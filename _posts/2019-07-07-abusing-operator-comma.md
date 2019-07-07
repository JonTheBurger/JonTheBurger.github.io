---
layout: post
title: Abusing Operator Comma
tags: [c++]
comments: true
---

First off, I'd like to preface this discussion by saying DO NOT DO THIS. There is currently a [proposal](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1161r2.html) to deprecate the use of the comma operator in subscripting expressions in order to allow for proper multidimensional overloads. This would allow us to write `array2d[0, 0]` rather than needing to rely on undesirable type nesting (for `array[0][0]`) or "abusing" the function call operator the way Eigen does `array2d(0, 0)`. In section 4, the proposal notably mentions the parsing library Boost Spirit Classic (deprecated since 2009) as one of the few real-world users of this comma abuse technique. Now, with that out of the way:

How many times are you working with your home-grown 2D matrix class and you accidentally mixed up indexing by X/Y vs indexing by Row/Col? Just a few short weeks ago I stumbled on this when rigging up a quick Tetris game. Indexing `std::array<std::array<T, COLS>,ROWS> arr` with `arr[x][y]` isn't just incorrect, it's _embarrassing_. Now, I of course read paragraph 1 of this article, so I didn't _actually do this_, but I did wonder if there was a way to leverage C++'s type-safe mechanisms to prevent me from making this mistake at compile time... (it's C++, so the answer is obviously "yes, with some effort.")

Using the power of user defined literals and overloading the comma operator, we can simulate multi-dimensional subscript operators, _and_ overload on types! We simply make types for Coordinates in forms of `X`, `Y`, `Row`, and `Column`. Next, create our user defined literals for convenience. Finally, create our comma operators and leverage a common `MatrixIndex` type, which interprets the coordinates in a common form.

{% highlight cpp %}
#include <array>
#include <iostream>

struct CoordinateX { size_t value; };
constexpr CoordinateX operator""_x(size_t x) { return { x }; }

struct CoordinateY { size_t value; };
constexpr CoordinateY operator""_y(size_t y) { return { y }; }

struct Col { size_t value; };
constexpr Col operator""_col(size_t col) { return { col }; }

struct Row { size_t value; };
constexpr Row operator""_row(size_t row) { return { row }; }

struct MatrixIndex {
  size_t row;
  size_t col;
};
constexpr MatrixIndex operator,(CoordinateX x, CoordinateY y) {
  return { y.value, x.value };
}
constexpr MatrixIndex operator,(Row row, Col col) {
  return { row.value, col.value };
}

template <typename T, size_t ROWS, size_t COLS>
class Matrix {
public:
  constexpr T& operator[](MatrixIndex idx) { return _matrix[idx.row][idx.col]; }

private:
  std::array<std::array<T, COLS>, ROWS> _matrix;
};

int main()
{
  Matrix<int, 3, 2> matrix{};

  matrix[0_row, 0_col] = 1;
  matrix[1_row, 0_col] = 2;
  matrix[2_row, 0_col] = 3;
  matrix[1_x, 0_y]     = 9;
  matrix[1_x, 1_y]     = 8;
  matrix[1_x, 2_y]     = 7;

  for (size_t row = 0; row < 3; ++row) {
    std::cout << "[ ";
    for (size_t col = 0; col < 2; ++col) {
      std::cout << matrix[Row{ row }, Col{ col }] << ", ";
    }
    std::cout << "]\n";
  }

  return 0;
}
{% endhighlight %}

And we get the following, just as we'd expect:

{% highlight bash %}
[ 1, 9, ]
[ 2, 8, ]
[ 3, 7, ]
{% endhighlight %}

For bonus points, compile with C++17 to get `constexpr` subscript operators on `std::array`. And vuala, you now have the power to perturb friends and coworkers alike.
