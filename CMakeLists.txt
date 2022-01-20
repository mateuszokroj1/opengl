cmake_minimum_required(VERSION 3.14)

project(OpenGLDemo)

	add_subdirectory(libs)

	add_executable(${PROJECT_NAME} WIN32 src/main.cpp)

	target_link_libraries(${PROJECT_NAME} glad_interface glfw)

option(PACKAGE_TESTS "Enable tests" ON)
if(PACKAGE_TESTS)
	enable_testing()
	add_subdirectory(tests)
endif()