cmake_minimum_required(VERSION 3.10)
project(ImGui_CMake_OpenGL)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(IMGUI_DIR ${CMAKE_SOURCE_DIR}/libs/imgui)
set(GLFW_DIR ${CMAKE_SOURCE_DIR}/libs/GLFW)

include_directories(${IMGUI_DIR} ${GLFW_DIR})

set(IMGUI_SRC
    ${IMGUI_DIR}/imgui.cpp
    ${IMGUI_DIR}/imgui_draw.cpp
    ${IMGUI_DIR}/imgui_widgets.cpp
    ${IMGUI_DIR}/imgui_impl_glfw.cpp
    ${IMGUI_DIR}/imgui_impl_opengl3.cpp
)

add_executable(ImGuiApp main.cpp ${IMGUI_SRC})

find_package(OpenGL REQUIRED)

add_subdirectory(${GLFW_DIR})

target_link_libraries(ImGuiApp glfw OpenGL::GL)