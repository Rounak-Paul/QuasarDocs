# Quasar Engine (PD) Programmer's Docoment

This document is the official Quasar Engine documentation. Visit [Quick Start](http://xyz) section for your first Quasar Project setup and build.

___
## Platforms

`Quasar Engine` is designed to be cross compatable between `Windows`, `Mac` and `Linux`. A single Codebase is managed for all three of these platforms. On Windows and Linux native implementation of `Vulkan` is used, while on Mac the Metal translation layer `MoltenVK` is used.

---
## Environment Setup
???+ info "Windows"
    * `Visual Studio` - [Visual Studio](https://visualstudio.microsoft.com) C++ devkit for Windows platform.
    * `CMake` - [CMake](https://cmake.org/download/) is a coss platform C++ build tool.
    * `Vulkan` - Graphics and compute API [Vulkan SDK](https://vulkan.lunarg.com). 

    Clone GitHub repo and with CMake run build. Make sure to clone the repo `recursively`.

___
## Quasar Dev Layout

    QuasarEngine
    |-Quasar                        # Engine dynamic library
    |   |-Include
    |   |-src
    |   |   |-Containers
    |   |   |-Core
    |   |   |-Editor
    |   |   |-Event
    |   |   |-Math
    |   |   |-Memory
    |   |   |-Resources
    |   |   |-Platform
    |   |   |-Renderer
    |   |   |-Systems
    |   |-Vendor
    |-Editor                        # User executable application (currently editor gui defined inside engine)
    |   |-src
    |-Assets
    |   |-fonts
    |   |-materials
    |   |-models
    |   |-textures
    |   |-shaders
    |-Project                       # User application, hot reload of user code
    |   |-src                      