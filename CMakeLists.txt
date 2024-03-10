cmake_minimum_required(VERSION 3.21)
project(Build)

#include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
#conan_basic_setup()

add_subdirectory(crossTemplateLib)
add_subdirectory(crossTemplateApp)
