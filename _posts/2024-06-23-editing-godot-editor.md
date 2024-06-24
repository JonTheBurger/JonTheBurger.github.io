---
layout: post
title: Editing the Godot Editor
tags: [c++, godot]
comments: true
---

This article will cover my experience playing with the Godot editor's source
code, and encapsulate practical examples of the lessons I try and teach juniors
that are navigating a new code-base for the first time.

# Preamble

If you want to get to the thick of things, skip this section. (If you're
anything like me, the first 10-15% of every youtube video or blog post being
irrelevant to the overall content drives you nuts, so I'm trying to help you
out!)

At the current stage of my career, mentoring has been one of my most important
responsibilities. I frequently find myself helping juniors cultivate the
techniques they'll need to navigate a large, foreign code-base (though the code
bases we put them on are hardly "large" in an absolute sense). Yet much of my
recent work touches the same handful of repos, many of which are at least partly
my brainchild. I couldn't help but realize that it had been some years since I
directly worked on a
[large, foreign code-base](https://github.com/TheMaverickProgrammer/OpenNetBattle/commit/4ed6b04323f5080a6b1a3bdc77faf2bf63df102d)...

I pondered this on the way to my summer vacation, where I would be meeting up
with my siblings, nieces, and nephews for the first time in half a year or so.
A particular children's exhibit we were visiting featured a Space-Invaders-like
game, an my nephews penchant for crushing any high score I set inspired me to
finally try out [RayLib](https://www.raylib.com/), and compare it with
[Godot](https://godotengine.org/) 4.2.2.

My earnest interest in making games began when I was around 12 years old, and my
sister bought me RPG Maker XP. While comfortable with a computer, I had no idea
how programming languages worked, so I was resigned to tweaking existing Ruby
scripts and programming logic through GUIs. Despite the tedium, I absolutely
loved making tile maps:

![]({{ site.baseurl }}/public/plains.png)
![]({{ site.baseurl }}/public/desert.png)

# The Mission

The most important tool in my tool-belt was the ellipse brush. After a few clicks,
it was virtually impossible to _not_ create interesting looking islands:

![]({{ site.baseurl }}/public/ellipse-rpgmaker.mp4)

This was my most desired missing feature when previously using Godot. To my
dismay, despite all of the excellent tile map additions they had made in the
past couple of years, an ellipse tool was still missing. And as such, my
adventure begins...

# From the Top Down

The great part about editing an application you have used before is that you
have existing keywords and concepts you can map from functionality back to
source code. For instance, looking at the "TileMap" editor, I can see there is
a "Rect" button:

![]({{ site.baseurl }}/public/godot-tiles.png)

These make for easy keyword searches. Looking at the godot repo, I see the following
directories:

```
|-- .github/
|-- core/
|-- doc/
|-- drivers/
|-- editor/
|-- main/
|-- misc/
|-- modules/
|-- platform/
|-- scene/
|-- servers/
|-- tests/
`-- thirdparty/
```

Clearly, I am working on the editor, so `editor` seems like a good bet for where
to search. The next directory down does not contain any files containing the
word "tile", so my search continues:

```
|-- debugger/
|-- export/
|-- gui/
|-- icons/
|-- import/
|-- plugins/
|-- project_manager/
|-- themes/
`-- translations/
```

I know Godot supports plugins, often applications that support plugins implement
core functionality in terms of plugins (QtCreator immediately coming to mind),
so I have a lucky first guess and check `plugins/`, which contains a `tiles/`
sub-directory. I open `tile_map_editor.cpp/.h` and I'm off to the races!

I want to place my "Ellipse" brush next to the "Rect" brush, so I simply search
for "rect" in the file, and vuala, the first text that greets me in the header
file is:

```cpp
Button *rect_tool_button = nullptr;
```

At this point, I feel confident that I'm at least on the right track, so now I
just need to see if I can build the code. Thankfully, the godot project has a
handy [Compiling From Source](https://github.com/godotengine/godot?tab=readme-ov-file#compiling-from-source)
link directly in its `README` file. Using the magic of "Reading the Friendly
Manual," I have Scons successfully building an x64 Debug project via Visual
Studio 2022*:

```bash
$ scons platform=windows vsproj=yes dev_build=yes
```

The docs even tell me I can build from within Visual Studio in the future. Neat!

# Adding a Button

All I do is copy and edit the line:

```cpp
Button *rect_tool_button = nullptr;
Button *ellipse_tool_button = nullptr;
```

Next comes a little bit of boilerplate. I just look for where `rect_tool_button`
is used and make a version using `ellipse_tool_button`. Here's an interesting
one: godot looks up an icon by name:

```cpp
source_sort_button->set_icon(tiles_bottom_panel->get_editor_theme_icon(SNAME("Sort")));
select_tool_button->set_icon(tiles_bottom_panel->get_editor_theme_icon(SNAME("ToolSelect")));
paint_tool_button->set_icon(tiles_bottom_panel->get_editor_theme_icon(SNAME("Edit")));
line_tool_button->set_icon(tiles_bottom_panel->get_editor_theme_icon(SNAME("Line")));
rect_tool_button->set_icon(tiles_bottom_panel->get_editor_theme_icon(SNAME("Rectangle")));
bucket_tool_button->set_icon(tiles_bottom_panel->get_editor_theme_icon(SNAME("Bucket")));
```

Surely there's an existing icon I can borrow. A lot of these names look pretty
generic, but "Bucket" seems specific and related enough to narrow down a search:

```bash
$ git ls-files '*Bucket*'
editor/icons/Bucket.svg
```

One match! Nice and easy! I simply look in that directory for an image name
"Elipse", then "Circle", and settle on "CircleShape2D":

```cpp
ellipse_tool_button->set_icon(tiles_bottom_panel->get_editor_theme_icon(SNAME("CircleShape2D")));
```

Compile (don't forget to select the `x64` configuration), debug, and I see some
success:

![]({{ site.baseurl }}/public/ellipse-button.png)

--------------------------------------------------------------------------------

*_As a NeoVim snob, I am contractually obligated to tell you that I usually use
neovim._
