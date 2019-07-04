---
layout: page
title: About
---

<p class="message">
  Jon maintains a strong passion for writing low level software with a focus on performance, expressiveness, and reliability. Modern software engineering is a collaborative effort, so supporting teams with ergonomic embedded tooling and libraries is top priority. He is just as eager to learn from incredible engineers as he is to share ideas, mentor, and collaborate.
  Lately, he has been enjoying refining his C++ abilities by catching up on major conferences, podcasts, and blogs. He then utilizes this knowledge to try and equip his coworkers with customizable, non-allocating equivalents of various standard library facilities, as well as the tools and knowledge to use them effectively.
</p>

Thanks for taking the time to visit! I try my best to share the useful and interesting programming and tooling techniques I've gathered in my travels in easily digestible, bite-sized pieces. It's my goal to make world class tooling for C++ accessible to the masses, so hopefully something here will be useful.

## Q&A

### How did you get started programming?
My first "language" was TI BASIC. In high school, one of my classmates put a quadratic solver program on my calculator that would always print "Made by Bob" upon completion. After learning how to remove that text, I wrote a temperature converter and used that as grounds to enroll in the second year CS course, which was in C++. Computer science and physics were the only classes I took in school that I felt required understanding more than memorization, so I tried to combine these in college by studying computer engineering.

### Is that why you use C++?
The ability to control the way my code behaves is priority #1 for me. Because the C++ community is extremely performance sensitive, they seem less willing to insist on a one size fits all approach. This respect combined with the incredible power of templates and explicit management of memory (shall I use SBO? An Allocator policy? pmr? COW? inplace storage? view?) keep me coming back.

### Is CMake worth stomaching?
Yes--meson and build2 look nice, but for now, cmake is the closest thing we've had to a standard build system. Besides, the basics are pretty easy. Just please, *please* make an effort to avoid assumptions based on IDE, generator, configuration/build type, compiler, environment, host OS, target, etc. And if I can `add_subdirectory` your module, you've already done me a huge favor.

### What are some of your favorite technical resources or discussions?
In roughly alphabetical order:
**Articles/Blogs**
- [A Heavily Commented Linux Kernel Source Code](http://www.oldlinux.org/download/ECLK-5.0-WithCover.pdf)
- [ARM Cortex-M, Interrupts and FreeRTOS: Part 1](https://mcuoneclipse.com/2016/08/14/arm-cortex-m-interrupts-and-freertos-part-1/)
- [Better Macros, Better Flags](https://www.fluentcpp.com/2019/05/28/better-macros-better-flags/)
- [Building Bare-Metal ARM Systems with GNU: Part 1 - Getting Started](https://www.embedded.com/design/mcus-processors-and-socs/4007119/Building-Bare-Metal-ARM-Systems-with-GNU-Part-1--Getting-Started)
- [Building the Convex Hull](http://www.drdobbs.com/architecture-and-design/building-the-convex-hull/201806315?pgno=1)
- [C99 Standard](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1256.pdf)
- [Clang command line argument reference](https://clang.llvm.org/docs/ClangCommandLineReference.html)
- [Creating a Fody Add-in](https://intellitect.com/creating-fody-addin/)
- [GBA Development](http://sebastianmihai.com/main.php?t=40)
- [GCC Command Options](https://gcc.gnu.org/onlinedocs/gcc/Invoking-GCC.html)
- [Game Programming Patterns](http://gameprogrammingpatterns.com/contents.html)
- [How Does the Internet Work?](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm)
- [How to Build a JRPG: A Primer for Game Developers](https://gamedevelopment.tutsplus.com/articles/how-to-build-a-jrpg-a-primer-for-game-developers--gamedev-6676#state)
- [Lazy Foo' Productions SDL Tutorial](http://lazyfoo.net/tutorials/SDL/)
- [Learning OpenGL](https://learnopengl.com/Introduction)
- [Linux-insides](https://0xax.gitbooks.io/linux-insides/)
- [Red Hat Enterprise Linux 4 - Using ld, the GNU Linker](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/4/html/Using_ld_the_GNU_Linker/index.html)
- [Red Hat Recommended compiler and linker flags for GCC](https://developers.redhat.com/blog/2018/03/21/compiler-and-linker-flags-gcc/)
- [SWIG for developers in a hurry](https://www.ibm.com/developerworks/aix/library/au-swig/index.html)
- [The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [The Amazing $1 Microcontroller](https://jaycarlson.net/microcontrollers/)
- [The Lost Art of Structure Packing](http://www.catb.org/esr/structure-packing/)
- [The Strict Aliasing Situation is Pretty Bad](https://blog.regehr.org/archives/1307)
- [Undefined Behavior in 2017](https://blog.regehr.org/archives/1520)
- [Understanding Flash: Blocks, Pages and Program / Erases](https://flashdba.com/2014/06/20/understanding-flash-blocks-pages-and-program-erases/)
- [Using ld The GNU linker - UUtah](https://www.math.utah.edu/docs/info/ld_toc.html)
- [Volatiles Are Miscompiled, and What to Do about It](https://www.cs.utah.edu/~regehr/papers/emsoft08-preprint.pdf)
- [What Every Programmer Should Know About Memory](https://people.freebsd.org/~lstewart/articles/cpumemory.pdf)
- [What every systems programmer should know about concurrency](https://assets.bitbashing.io/papers/concurrency-primer.pdf)
- [Why Most Unit Testing is Wasteful](https://rbcs-us.com/documents/Why-Most-Unit-Testing-is-Waste.pdf)
- [Windows 10 Development Environment](https://developer.microsoft.com/en-us/windows/downloads/virtual-machines)
- [Writing ARM Assembly](https://azeria-labs.com/writing-arm-assembly-part-1/)

**Books**
- Clean Code
- Deep C Secrets
- Effective C++
- Effective Modern C++
- Game Programming Patterns
- Making Embedded Systems: Design Patterns for Great Software
- Modern C++ Design
- Working Effectively With Legacy Code

**Conference Talks**
- [GoingNative 2013: Sean Parent - C++ Seasoning](https://youtu.be/W2tWOdzgXHA)
- [CppCon 2014: Mike Acton - Data-Oriented Design and C++](https://youtu.be/rX0ItVEVjHc)
- [CppCon 2015: Andrei Alexandrescu - Declarative Control Flow](https://youtu.be/WjTrfoiB0MQ)
- [CppCon 2015: Andrei Alexandrescu - std::allocator](https://youtu.be/LIb3L4vKZ7U)
- [CppCon 2015: Sean Parent - Better Code: Data Structures](https://youtu.be/sWgDk-o-6ZE)
- [CppCon 2016: Herb Sutter - Leak-Freedom in C++... By Default.](https://youtu.be/JfmTagWcqoE)
- [CppCon 2016: Nicholas Ormrod - The strange details of std::string at Facebook](https://youtu.be/kPR8h4-qZdk)
- [CppCon 2016: Timur Doumler - Want fast C++? Know your hardware!](https://youtu.be/BP6NxVxDQIs)
- [CppCon 2017: Bob Steagall - How to Write a Custom Allocator](https://youtu.be/kSWfushlvB8)
- [CppCon 2017: Carl Cook - When a Microsecond Is an Eternity: High Performance Trading Systems in C++](https://youtu.be/NH1Tta7purM)
- [CppCon 2017: Herb Sutter - Meta: Thoughts on generative C++](https://youtu.be/4AfRAVcThyA)
- [CppCon 2017: James McNellis - Everything You Ever Wanted to Know about DLLs](https://youtu.be/JPQWQfDhICA)
- [CppCon 2017: John Lakos - Local ('Arena') Memory Allocators (part 1 of 2)](https://youtu.be/nZNd5FjSquk)
- [CppCon 2017: Louis Brandy - Curiously Recurring C++ Bugs at Facebook](https://youtu.be/lkgszkPnV8g)
- [CppCon 2017: Matt Kulukundis - Designing a Fast, Efficient, Cache-friendly Hash Table, Step by Step](https://youtu.be/ncHmEUmJZf4)
- [CppCon 2017: Nir Friedman - What C++ developers should know about globals (and the linker)](https://youtu.be/xVT1y0xWgww)
- [CppCon 2017: Pablo Halpern - Allocators: The Good Parts](https://youtu.be/v3dz-AKOVL8)
- [CppCon 2017: Stephen Dewhurst - Modern C++ Interfaces](https://youtu.be/PFdWqa68LmA)
- [NDC 2018: Joe Albahari - Writing a Neural Net from Scratch](https://youtu.be/z8DY5DndmxI)
- [CppCon 2018: Jeff Trull - Liberating the Debugging Experience with the GDB Python API](https://youtu.be/ck_jCH_G7pA)
- [CppCon 2018: Michael Caisse - Modern C++ in Embedded Systems - The Saga Continues](https://youtu.be/LfRLQ7IChtg)
- [CppCon 2018: Tom Poole - Why and How to Roll Your Own std::function Implementation](https://youtu.be/VY83afAJUIg)
- [C++Now 2018: Arthur O'Dwyer - The Best Type Traits that C++ Doesn't Have](https://youtu.be/MWBfmmg8-Yo)
- [C++Now 2018: Z. Laine - Boost.Text: Fixing std::string, and Adding Unicode to Standard C++](https://youtu.be/944GjKxwMBo)
- [C++Now 2019: Arthur O'Dwyer - Boost.Blockchain: A new business model for open source](https://youtu.be/2v2N12xeruc)
- [C++Now 2019: Arthur O'Dwyer - Trivially Relocatable](https://youtu.be/SGdfPextuAU)
- [C++Now 2019: Michael Caisse - Embedded Domain Specific Languages for Embedded Bare Metal Projects](https://youtu.be/OkeRijjmoh8)

**Podcasts**
- [CppCast 26: Effective C++ with Scott Meyers](http://cppcast.com/2016/01/matt-godbolt/)
- [CppCast 37: Ranges with Eric Niebler](http://cppcast.com/2015/12/eric-niebler/)
- [CppCast 82: Catch 2 and C++ the Community with Phil Nash](http://cppcast.com/2015/05/phil-nash/)
- [CppCast 88: Microsoft's STL with Stephan T. Lavavej](http://cppcast.com/2017/02/stephan-lavavej/)
- [CppCast 93: C++ Game Development at Blizzard with Ben Deane](http://cppcast.com/2017/03/ben-deane/)
- [CppCast 98: Hippomocks and cpp-dependencies with Peter Bindels](http://cppcast.com/2017/04/peter-bindels/)
- [CppCast 100: Past, Present and Future of C++ with Bjarne Stroustrup](http://cppcast.com/2017/05/bjarne-stroustrup/)
- [CppCast 133: Compiler Explorer with Matt Godbolt](http://cppcast.com/2016/01/matt-godbolt/)
- [CppCast 133: Meltdown and Spectre with Matt Godbolt](http://cppcast.com/2018/01/matt-godbolt/)
- [CppCast 150: Freestanding Proposal with Ben Craig](http://cppcast.com/2018/05/ben-craig/)
- [CppCast 153: Vcpkg with Robert Schumacher](http://cppcast.com/2018/06/robert-schumacher/)
- [CppCast 160: Parallel Ranges with Christopher Di Bella](http://cppcast.com/2018/07/chris-dibella/)
- [CppCast 195: fmt with Victor Zverovich](http://cppcast.com/2019/04/victor-zverovich/)
- [Embedded.fm 137: Pausing to think](https://embedded.fm/episodes/137repeat)
- [Embedded.fm 273: Swiss knife of embedded systems](https://embedded.fm/episodes/274)

**Repos/Libraries**
- [Asio](https://github.com/chriskohlhoff/asio/)
- [Awesome C++](https://github.com/fffaraz/awesome-cpp)
- [Awesome CMake](https://github.com/onqtam/awesome-cmake)
- [Boost.Mp11](https://github.com/boostorg/mp11)
- [Boost.SML](https://github.com/boost-experimental/sml)
- [Boost.Signals2](https://github.com/boostorg/signals2)
- [Boost.Spirit](https://github.com/boostorg/spirit)
- [Boost.Stacktrace](https://github.com/boostorg/stacktrace)
- [Catch2](https://github.com/catchorg/Catch2)
- [Cereal](https://github.com/USCiLab/cereal)
- [Cmsis-svd (python)](https://github.com/posborne/cmsis-svd)
- [Cotire](https://github.com/sakra/cotire)
- [EASTL](https://github.com/electronicarts/EASTL)
- [Etl](https://github.com/ETLCPP/etl)
- [Fmt](https://github.com/fmtlib/fmt)
- [GUnit](https://github.com/cpp-testing/GUnit)
- [Hedley](https://github.com/nemequ/hedley)
- [Hippomocks](https://github.com/dascandy/hippomocks)
- [Libelfin](https://github.com/aclements/libelfin)
- [LittlevGL](https://littlevgl.com/)
- [Live Charts (C#)](https://lvcharts.net/)
- [Magic_enum](https://github.com/Neargye/magic_enum)
- [Nlohmann-json](https://github.com/nlohmann/json)
- [Pitchfork](https://github.com/vector-of-bool/pitchfork)
- [Pybind11](https://github.com/pybind/pybind11)
- [Qt Advanced Docking System](https://github.com/mfreiholz/Qt-Advanced-Docking-System)
- [Qt Node Editor](https://github.com/paceholder/nodeeditor)
- [Qt](https://doc.qt.io/qt-5/reference-overview.html)
- [Qwt](https://qwt.sourceforge.io/)
- [ROS](http://wiki.ros.org/)
- [Ranges-v3](https://github.com/ericniebler/range-v3)
- [Spdlog](https://github.com/gabime/spdlog)
- [Units](https://github.com/nholthaus/units)
- [Vcpkg](https://github.com/microsoft/vcpkg)

### What software do you use?
When it comes to development, I have a few staples:
- QtCreator - Excellent vim bindings, nearly everything can be bound to a hotkey, clang based completion, cross platform, and fast.
- zsh - Everything a terminal should be, really.
- vim - I was reluctant to learn, but once liberal use of Home and End didn't cut it anymore, I never looked back. Still a bit reluctant to dive into neovim though.
- vscode - I've only liked vscode more and more as time goes on--best extension ecosystem hands down. It's gone so far as to replace pycharm for me. The fact it can chug would almost always be a dealbreaker, but this is the only program that's good enough for me to tolerate it.
- [godbolt compiler explorer](https://gcc.godbolt.org/) - Awesome assembly translation tool.
- sublime text - A blindingly fast, simple editor for pasting quick notes or logs.
- vmware - Snapshots have saved me so many times, it's earned a spot on this list.
- Ninja - Are you using CMake? Great. Stop using make now.
- Ccache - A couple lines of CMake and your clean rebuilds are magically faster. It doesn't get better than that.
- KCachegrind - Makes the already incredible cachegrind gorgeous.
- Massif Visualizer - Heap allocation tracker GUI.

Some underappreciated gems:
- cutecom - Build from the gitlab sources and treat yourself to the best serial terminal out there. Customizable macro buttons, recent commands list, and all the TX/RX, logging, and formatting options you'd expect.
- JLink OZone Debugger - If you have a JLink PRO and an elf file, you've got a very powerful embedded focused debugger at your fingertips. Nice memory map view and trace utilities make it an unsung hero for those that can actually use it.
- OpenCppCoverage - If you have an MSVC binary, you can get coverage results pretty hassle free. I guess visual studio probably has built in support for this sort of thing, but if you want a build server friendly solution, give it a chance!
- SourceTrail - Very interesting source navigation and visualization tool. Definitely worth a look.
- Chocolatey - Feels like it sort of fell by the wayside, but I want to believe a comeback is coming!

What about fun?
- Redshift/Flux - Required for staying up too late trying to get your cross compiler working.
- OBS Studio - Excellent recording software. Used for any videos I make.
- Audacity - Great for editing audio tracks, and make sure you don't cause anyone ear damage. 
- KDenLive - Nice video editor, and I'm a sucker for Qt and KDE.
- Synergy - Proprietary (I think you can build from source?), but extremely handy for doing simultaneous laptop/desktop work.
- Foxit Reader - PDF reader of choice. Multiple tabs, pdf editing, etc.
- ScreenToGif - Windows application for making gifs, painlessly.
- Paint.NET - Best simple paint application, hands down. Windows only.
- Godot - Promising MIT licensed game engine that actually gives 2D a first-class spot at the table.
- LMMS - Open source digital music synthesizer with tons of preset samples. I use it to make (terrible?) music.
- Krita - Digital art application I occasionally use to paint (terrible?) art.
- Tiled - Fun tile mapper program--decent for DnD mapping.
- Aseprite - Simply awesome sprite editing program. Proprietary, but you can build from source (though not redistribute binaries)!

### What do you do other than programming?
Though I'm not particularly good at my other hobbies, I do enjoy
- Cooking
- Singing
- Playing the next MegaMan or Zelda game, whenever someone decide to make one.
- Fitness training and dieting
- Learning guitar

### How about some random ice breakers?
- Favorite Animal? - Fox
- Favorite Karaoke? Song - Don't Stop Me Now by Queen
- Favorite Desert? - Anything with Oreos
- Favorite Food? - Deep dish pizza, or macaroni and cheese
- Favorite Sport? - Soccer
- How do you take your steak? - Rare with coarse salt
- How do you take your coffee? - Black, medium roasts preferred
- Would you rather fight 100 duck sized horses or 1 horse sized duck? - Obviously 100 duck sized horses
