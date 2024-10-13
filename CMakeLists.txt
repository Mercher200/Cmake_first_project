cmake_minimum_required(VERSION 3.10)
project(ImGui_CMake_OpenGL)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(libs/imgui)
add_subdirectory(libs/GLFW)
add_subdirectory(libs/backend)

find_package(OpenGL REQUIRED)

add_executable(cmake_imgui main.cpp)

target_link_libraries(cmake_imgui PUBLIC imgui GLFW backend OpenGL::GL)
