cmake_minimum_required(VERSION 3.5)

project(cmake_example_2)

set(cmake_example_2_VERSION_MAJOR 1)
set(cmake_example_2_VERSION_MINOR 2)
set(cmake_example_2_VERSION_PATCH 3)
set(cmake_example_2_VERSION_TWEAK 4)
set(cmake_example_2_VERSION "${cmake_example_2_VERSION_MAJOR}.${cmake_example_2_VERSION_MINOR}.${cmake_example_2_VERSION_PATCH}.${cmake_example_2_VERSION_TWEAK}")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++1y -Wall -O2")

file(GLOB 
            CPPS "src/*.cpp")

configure_file(
                    "${PROJECT_SOURCE_DIR}/include/ver.h.in"
                    "${PROJECT_BINARY_DIR}/include/version.h"
                    )

configure_file(
    "${PROJECT_SOURCE_DIR}/include/path.h.in"
    "${PROJECT_BINARY_DIR}/include/path.h"
    )

include_directories("${PROJECT_SOURCE_DIR}/include")
include_directories("${PROJECT_BINARY_DIR}/include")
add_executable(${PROJECT_NAME} ${CPPS})