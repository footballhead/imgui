cmake_minimum_required(VERSION 3.5 FATAL_ERROR)
project(imgui C CXX)

add_definitions("-Wall -Wformat")

#
# imgui (main lib)
#

add_library(imgui STATIC
	imgui.cpp
	imgui_demo.cpp
	imgui_draw.cpp
	imgui_widgets.cpp
	)
target_include_directories(imgui PUBLIC
	.
	)

#
# examples
#

add_subdirectory(examples)
