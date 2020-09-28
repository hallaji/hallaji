---
title: 'Classic Game: Crossing the Barriers by Airplane'
date: '2014-02-23'
tags:
  - opengl
  - c++
  - game
seo:
  title: 'Classic Game: Crossing the Barriers by Airplane'
  description: A simple game with C++ and OpenGL published on Github
  openGraph:
    images:
      - url: 'https://hallaji.com/blog/crossing-barriers-airplane-opengl/screenshot.jpg'
        width: 596
        height: 596
        alt: Screenshot of Crossing the Barriers
---

[repo]: https://github.com/hallaji/crossing-barriers
[wiki]: https://en.wikipedia.org/wiki/Silicon_Graphics
[download]: https://github.com/hallaji/crossing-barriers/archive/master.zip
[screenshot]: /blog/crossing-barriers-airplane-opengl/screenshot.jpg

OpenGL is an API for rendering 2D and 3D vector graphics. The API is used to interact with a graphics processing unit
(GPU) to achieve hardware-accelerated rendering and it was developed by [Silicon Graphics Inc][wiki]. A long time ago,
I programmed a simple game with `C++` and `OpenGL` and published it on a [Github][repo] repo.

---

![Screenshot][screenshot]

## Step 1

You should have OpenGL utility toolkit on your computer to compile and run the source. First [download][download] the
source that contains a folder named as `glut-3.7.6-bin`. Then go to the Microsoft Visual Studio installation folder and
copy the files as below:

```bash
Copy  glut.h      ->    \vc\include\
Copy  glut32.dll  ->    \vc\lib\
```

Also you should copy `.lib` file to both Windows system folders:

```bash
Copy  glut32.lib  ->   \Windows\System
                       \Windows\System32
```

## Step 2

The `Bricks.raw` file is a bricks pattern that I exported from the photoshop. If you want to change the pattern, first
open your desired image with photoshop and save it again as a `.raw` file. Finally, you must copy this file near your
`.exe` within debug directory before running the project in Visual Studio.
