cmake_minimum_required(VERSION 3.15)
project(ImGui LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Actual static library
file(GLOB_RECURSE SOURCE_DIR 
    "imconfig.h"
    "imgui.h"
    "imgui.cpp"
    "imgui_draw.cpp"
    "imgui_internal.h"
    "imgui_tables.cpp"
    "imgui_widgets.cpp"
    "imstb_rectpack.h"
    "imstb_textedit.h"
    "imstb_truetype.h"
    "imgui_demo.cpp"

    "backends/imgui_impl_glfw.h"
    "backends/imgui_impl_glfw.cpp"
    "backends/imgui_impl_opengl3.h"
    "backends/imgui_impl_opengl3.cpp"
    "backends/imgui_impl_opengl3_loader.h"
)

add_library(ImGui STATIC ${SOURCE_DIR})
target_include_directories(ImGui PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")
target_link_libraries(ImGui PUBLIC glfw)