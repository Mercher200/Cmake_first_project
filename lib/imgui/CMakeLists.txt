cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 11)

add_library(imgui STATIC imconfig.h  imgui_draw.cpp imgui_internal.h imgui_widgets.cpp imgui.cpp imgui.h imstb_rectpack.h imstb_textedit.h imstb_truetype.h)

find_package(OpenGL REQUIRED)

target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(imgui PUBLIC OpenGL::GL)
