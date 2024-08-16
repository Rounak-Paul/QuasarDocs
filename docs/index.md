# Quasar Engine (PD) Programmer's Docoment

This document is targeted towards the development of Quasar Engine and its plugins. For User's Decument (UD) visit [Quasar Engine (UD) User's Decoment](http://xyz).

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
## Project Layout

    QuasarEngine
    |-Quasar                        # Engine dynamic library
    |   |-src
    |   |   |-Core
    |   |   |-Event
    |   |   |-Math
    |   |   |-Platform
    |   |   |-Renderer
    |   |-Include
    |   |-Vendor
    |-Editor                        # User executable application
    |   |-src
    |-Assets
    |   |-shaders                   # Assets to be copied to bin
    |-Project                       # User application, hot reload of user code