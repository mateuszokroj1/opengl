cmake_minimum_required(VERSION 3.14)

add_subdirectory(framework)

set(GLFramework_SharedBuild ON)
set(GLFramework_BuildTests OFF)

project(OpenGLDemo)

	add_executable(${PROJECT_NAME} WIN32 src/main.cpp)