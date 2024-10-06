cmake_minimum_required(VERSION 3.10)
project(ImGui)

file(GLOB IMGUI_SOURCES *.cpp)

add_library(imgui ${IMGUI_SOURCES})
target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
