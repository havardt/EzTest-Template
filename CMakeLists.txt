cmake_minimum_required (VERSION 2.8)

project (eztest_template)

set (PROJECT_VERSION_MAJOR 0)
set (PROJECT_VERSION_MINOR 0)
set (PROJECT_VERSION_PATCH 0)

set (CMAKE_C_STANDARD 11)

if (CMAKE_COMPILER_IS_GNUCC)
    set(CMAKE_C_FLAGS "-Wall")
    set(CMAKE_C_FLAGS_DEBUG "-g")
    set(CMAKE_C_FLAGS_RELEASE "-O3")
endif()

add_subdirectory (src)
add_subdirectory (test)

enable_testing ()

add_test (NAME unit_test COMMAND eztest_runner)
