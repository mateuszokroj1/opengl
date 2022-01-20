cmake_minimum_required(VERSION 3.14)

project(OpenGLDemo)

	#include_directories(${OPENGL_INCLUDE_DIR})

	IF(APPLE)
		INCLUDE_DIRECTORIES ( '/System/Library/Frameworks' )
		FIND_LIBRARY(OpenGL_LIBRARY OpenGL )
		MARK_AS_ADVANCED (COCOA_LIBRARY
			GLUT_LIBRARY
			OpenGL_LIBRARY)
		SET(EXTRA_LIBS ${COCOA_LIBRARY} ${GLUT_LIBRARY} ${OpenGL_LIBRARY})
	ENDIF()

	add_subdirectory(libs)

	if(WIN32)
		add_executable(${PROJECT_NAME} WIN32 src/main.cpp)
	else()
		add_executable(${PROJECT_NAME} src/main.cpp)
	endif()

	target_link_libraries(${PROJECT_NAME} ${OpenGL_LIBRARY} glad_interface glfw)

option(PACKAGE_TESTS "Enable tests" ON)
if(PACKAGE_TESTS)
	enable_testing()
	add_subdirectory(tests)
endif()