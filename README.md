Objectives

The objective for this project is to show that you have acquired programming logic and that you are able to adapt to new languages.

The programming language you are about to use is C++. Creating a project from scratch will not be asked, instead you will have to add features or fix the code of a given application.

The application you are about to work on is a Desktop System Monitor. The app will monitor the computer system resources and performance, such as CPU, RAM, SWAP, Fan, Network and more. For the GUI you will use the Dear ImGui library for C++.
Instructions
Dear ImGui

As stated above the GUI you are going to use is Dear ImGui there are some notions you should know about this library/API.

The first important point to be aware of is that ImGui is an immediate mode graphic user interface, as the name implies it: "ImGui". There are two types of UIs, retained mode and immediate mode.

    Immediate mode: the application state is separated from the graphics library. It is the application responsibility for drawing commands when necessary. In other words, in immediate mode the client calls directly results in the rendering of graphics objects to the display.

    Retained mode: the client calls do not directly cause actual rendering, but instead update an abstract internal model, which is maintained within the library's data space. You can see more about this mode here.

For this API there is no need for specific builds, you can add the files to your existing project. To integrate Dear ImGui you must use a backend, this backend passes mouse/keyboard/gamepad inputs and a variety of settings. It is in charge of rendering the resulting vertices.

The backend will be provided by us, in a file system described in the next paragraph. You will have to install sdl by running the command apt install libsdl2-dev.
File System

The file system provided, here, will contain all the ImGui IPA. For easier understanding, see below a representation of the fs.

$ tree system-monitor
├── header.h
├── imgui                                 // <-- ImGui APIs
│   └── lib
│       ├── backend                       // <-- ImGui backend
│       │   ├── imgui_impl_opengl3.cpp
│       │   ├── imgui_impl_opengl3.h
│       │   ├── imgui_impl_sdl.cpp
│       │   └── imgui_impl_sdl.h
│       ├── gl3w
│       │   └── GL
│       │       ├── gl3w.c
│       │       ├── gl3w.h
│       │       └── glcorearb.h
│       ├── imconfig.h
│       ├── imgui.cpp
│       ├── imgui_demo.cpp
│       ├── imgui_draw.cpp
│       ├── imgui.h
│       ├── imgui_internal.h
│       ├── imgui_tables.cpp
│       ├── imgui_widgets.cpp
│       ├── imstb_rectpack.h
│       ├── imstb_textedit.h
│       └── imstb_truetype.h
├── main.cpp                             // <-- main file, where the application will
├── Makefile                             //     render (main loop)
├── mem.cpp                              // <-- memory resources and processes information
├── network.cpp                          // <-- network resources
└── system.cpp                           // <-- all system resources

5 directories, 28 files

Linux and Proc

To monitor the computer system resources and performance you will have to use the /proc filesystem.

The /proc filesystem is a virtual system that does not exist on disk. This system is created by the kernel when the system boots, and destroyed by it when the system shuts down.

This filesystem contains information about the system, from the CPU, to memory, to active processes and much more. For this reason, it can be regarded as a control and information center for the kernel. As a matter of fact, a lot of the system utilities are simple calls to files in this directory.

You can acquire more knowledge about this filesystem by taking a look to the proc manual page (man proc).