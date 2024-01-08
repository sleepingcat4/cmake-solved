cmake_minimum_required(VERSION 3.22)
project(HelloWorld VERSION 1.0 LANGUAGES CXX)

set(CMAKE_TOOLCHAIN_FILE "C:/src/vcpkg/scripts/buildsystems/vcpkg.cmake")

# Set the installation prefix for raylib
list(APPEND CMAKE_PREFIX_PATH "C:/src/vcpkg/packages/raylib_x64-windows")

# Set the C++ compiler for MinGW
if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
    set(CMAKE_CXX_COMPILER "C:/Program Files/mingw-w64/x86_64-8.1.0-posix-seh-rt_v6-rev0/mingw64/bin/g++.exe")
    set(CMAKE_CXX_STANDARD 11)  # or the C++ standard you want to use
endif()

find_package(raylib REQUIRED)

add_executable(world hello_world.cpp)
target_include_directories(world PRIVATE "C:/src/vcpkg/packages/raylib_x64-windows/include")
target_link_libraries(world PRIVATE raylib)
