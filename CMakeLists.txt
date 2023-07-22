# CMake Specifications --------------------------------------------------------
cmake_minimum_required(VERSION 3.6)

# C++ Standard Specifications -------------------------------------------------
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

project(base-imgui VERSION 0.1)

find_package(SDL2 REQUIRED)
find_package(Vulkan REQUIRED)

add_subdirectory(src)