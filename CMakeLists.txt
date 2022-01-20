cmake_minimum_required(VERSION 3.14)

project(OpenGLDemo)

	find_package(OpenGL REQUIRED)
	add_subdirectory(libs)

	if(WIN32)
		add_executable(${PROJECT_NAME} WIN32 src/main.cpp)
	else()
		add_executable(${PROJECT_NAME} src/main.cpp)
	endif()

	target_link_libraries(${PROJECT_NAME} opengl32 glad_interface glfw)

option(PACKAGE_TESTS "Enable tests" ON)
if(PACKAGE_TESTS)
	enable_testing()
	add_subdirectory(tests)
endif()