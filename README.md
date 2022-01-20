# OpenGL demo project
OpenGL demo project with C++, CMake and GLFW3, GLAD.

## Development requirements

* Any IDE (recommended VisualStudio or VS Code)
* Any C++ compiler running on x64 mode
* CMake min. version 3.14

## Cloning

Please set `git config --global submodule.recurse true` before you clone this repo.
This setting will make the repository pick up submodules correctly.

## Build

1. Open Bash/Terminal/PowerShell and go to directory, where Git repo is located.
2. Prepare cache files with CMake: `cmake --preset "x64-Debug"`
3. Build your project: `cmake --build`

The final object is a OpenGL windowed app.
