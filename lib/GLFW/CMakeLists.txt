cmake_minimum_required(VERSION 3.10)
project(GLFW)

file(GLOB GLFW_SOURCES src/*.c)

if(NOT GLFW_SOURCES)
    message(FATAL_ERROR "No source files found for GLFW!")
endif()

add_library(glfw ${GLFW_SOURCES})
target_include_directories(glfw PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
