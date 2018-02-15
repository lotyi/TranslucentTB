﻿# TranslucentTB

[![Build status](https://ci.appveyor.com/api/projects/status/9yym3vr6s5gc7vk3/branch/develop?svg=true)](https://ci.appveyor.com/project/sylveon/translucenttb/branch/develop)
[![Join on Discord](https://img.shields.io/discord/304387206552879116.svg)](https://discord.gg/w95DGTK)
[![Join the chat at https://gitter.im/TranslucentTB/Lobby](https://badges.gitter.im/TranslucentTB/Lobby.svg)](https://gitter.im/TranslucentTB/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Total downloads](https://img.shields.io/github/downloads/TranslucentTB/TranslucentTB/total.svg)](https://github.com/TranslucentTB/TranslucentTB/releases)

A lightweight (uses a few MB of RAM and almost no CPU) utility that makes the Windows taskbar translucent/transparent on Windows 10.

You can see examples of the customizations you can make in the images below:

![](https://charles.getsharex.com/GbOX4b.png) ![](https://charles.getsharex.com/yX37Vc.png) ![](https://charles.getsharex.com/MPaxeO.png)

## Features

TranslucentTB supports multiple taskbar states and dynamic taskbar states.

 - Advanced **color picker** supporting alpha to change the taskbar's color.
 - **Taskbar states** (choose one):
   - **Blur**: Will make the taskbar slightly blurred.
   - **Clear**: Transparent taskbar.
   - **Normal**: Classic Windows style.
   - **Opaque**: No transparency.
   - **Fluent**: Windows Insider build higher than 17063 only. Will give the taskbar an appearance similar to Microsoft's Fluent Design guidelines.
 - **Dynamic** modes (these can be used together):
   - **Dynamic Windows**: Will change the taskbar to a different state if a window is currently maximised.
   - **Dynamic Peek**: Will hide the Aero Peek button if no window is currently maximised.
   - **Dynamic Start Menu**: Will restore default taskbar appearance when the start menu is opened.
 - Ability to **show or hide the Aero Peek** button.

You can see it in action [here](https://gfycat.com/EverlastingCreamyIlladopsis) (Thanks [@Gunny123](https://github.com/Gunny123)!).

## Download

You can download the program (prebuilt executables and source snapshots) [via the releases tab](https://github.com/TranslucentTB/TranslucentTB/releases).
If you want to get the latest bleedging edge build, you can grab it over at the [AppVeyor artifacts](https://ci.appveyor.com/project/sylveon/translucenttb/build/artifacts). Note that these build may not work, or include features that are partially complete. Use at your own risk.

## Add to Startup

To add TranslucentTB to startup, check the "Open at boot" entry in the TranslucentTB tray icon's context menu. If it is grayed out, TranslucentTB startup has been disabled from the Task Manager.

## Security

Some antiviruses are over eager, so they might flag this program as malicious. IT IS NOT! Over 150 thousand users have downloaded this program safely. The source is open, you can compile it yourself, and I welcome any and all security reviews.

Speaking of compiling...

## Building from source

You can checkout one of the available branches. However, it recommended to use `master`, as the code here is stable and has been passed through peer review.

Via [git](https://git-scm.com):
```
$ git clone -b <branch-you-want> https://github.com/TranslucentTB/TranslucentTB
Cloning into 'TranslucentTB'...
remote: Counting objects: 909, done.
remote: Compressing objects: 100% (40/40), done.
remote: Total 909 (delta 44), reused 61 (delta 35), pack-reused 834
Receiving objects: 100% (909/909), 383.94 KiB | 2.78 MiB/s, done.
Resolving deltas: 100% (624/624), done.
```

You can also download a zip archive of each branch by clicking on the `Clone or download` button while browsing that branch's files.

Now that you have the source, you will need Visual Studio 2017. [You can get the free community edition here](https://www.visualstudio.com/vs/community/).
You will also need the Visual Studio _2015_ C++ Build Tools; **The VS 2017 Build Tools will not work with Clang.** [They can be downloaded here.](http://landinghub.visualstudio.com/visual-cpp-build-tools)

You also need the [Clang compiler for Windows](http://releases.llvm.org/download.html). Install this after you install the VS2015 Build Tools.

Once you have that installed (make sure you have the C++ components and Windows SDK 10.0.16299 installed). Then you can open TranslucentTB.sln, and press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> to build the solution.
The output will be in either the Release or Debug folder (depending on which configuration is currently active).

If you don't want to open Visual Studio (or install it), you can install the [Visual C++ Build Tools](http://landinghub.visualstudio.com/visual-cpp-build-tools), the [Windows SDK](https://developer.microsoft.com/en-US/windows/downloads/windows-10-sdk) version 10.0.16299 and the [Clang compiler for Windows](http://releases.llvm.org/download.html). The C++ build tools and Windows SDK are already included in Visual Studio.

Then open the `Visual C++ MSBuild Command Prompt` (or `Developer Command Prompt for VS 2017`) and `cd` into the root directory of this project, before running `msbuild /p:Configuration=Release`.

## Thanks

TTB is a team effort! It is the result of the collective efforts of many people:
 - [@ethanhs](https://github.com/ethanhs),
 - [@sylveon](https://github.com/sylveon),
 - [@MrAksel](https://github.com/MrAksel),
 - [@denosawr](https://github.com/denosawr),
 - [@PFCKrutonium](https://github.com/PFCKrutonium).

If you would like to contribute, everyone is welcome to! If you are considering a major feature, need guidance, 
or want to talk an idea out, don't hesitate to jump on Discord or Gitter (see the badges on the top of the README), or file an issue here. The main contributors are often on Discord, Gitter and GitHub, so we should reply fairly quickly.
Also, at this time I have no plans of expanding this beyond the taskbar.

The color picker used comes from [this great CodeProject article](https://www.codeproject.com/Articles/9207/An-HSV-RGBA-colour-picker).
The code has been slightly changed to fix a few bugs, warnings and errors in newer Visual Studio versions.

### Similar programs

If you are looking for something that modifies more than just the taskbar, there are several programs out there.

[Taskbar Tools](https://github.com/Elestriel/TaskbarTools) is a similar program written in C#. Please note that it seems to be unmaintaned.

You may have seen similar translucency abilities from programs such as StartIsBack, Start10 and the now defunct Classic Shell. All of these are great programs, but I don't need the start-replacement features, so I wrote this.
Also, Dynamic States allow for more customisability over the taskbar.

### License

This program is free software under the GPL v3. Please see the LICENSE.md file for more.
