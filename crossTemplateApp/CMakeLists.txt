cmake_minimum_required(VERSION 3.21)
project(application)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(LIB_DIR "${CMAKE_SOURCE_DIR}/crossTemplateLib")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

file(GLOB headers"${LIB_DIR}/include/NativeLib.h")
file(GLOB sources "${CMAKE_SOURCE_DIR}/crossTemplateApp/src/main.cpp")

add_executable(application ${sources})
target_include_directories(application PUBLIC ${headers})

source_group(TREE "${LIB_DIR}/include" PREFIX "Header Files" FILES ${headers})

target_include_directories(application PRIVATE "${LIB_DIR}/include")

target_link_libraries(application crosslib)
