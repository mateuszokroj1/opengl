add_subdirectory(libs/gtest)

if(WIN32)

    set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

endif()

project(Tests)

    set(sources
        src/test.cpp
    )

    add_executable(${PROJECT_NAME} ${sources})

    target_link_libraries(${PROJECT_NAME} GTest::gtest_main)

    add_test(NAME TestGroup COMMAND Test)