cmake_minimum_required(VERSION 3.5)

project(ImGuiFileDialog)

find_package(imgui CONFIG REQUIRED)

add_library(ImGuiFileDialog STATIC
    ImGuiFileDialog.cpp
    ImGuiFileDialog.h
    ImGuiFileDialogConfig.h
)

target_include_directories(ImGuiFileDialog PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(ImGuiFileDialog PRIVATE imgui::imgui)

if(UNIX)
    target_compile_options(ImGuiFileDialog PUBLIC -Wno-unknown-pragmas)
endif()
