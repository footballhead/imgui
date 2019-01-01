project(imgui_examples C CXX)

# If SDL is installed through brew or apt then CONFIG will find it without a custom FindSDL2.cmake
find_package(SDL2 REQUIRED CONFIG)
find_package(OpenGL REQUIRED)

#
# imgui_impl_sdl_opengl2
#

add_library(imgui_impl_sdl_opengl2 STATIC
	imgui_impl_opengl2.cpp
	imgui_impl_sdl.cpp
	)
target_include_directories(imgui_impl_sdl_opengl2
	PUBLIC
		.
		${SDL2_INCLUDE_DIRS}
	PRIVATE
		${OPENGL_INCLUDE_DIR}
	)
target_link_libraries(imgui_impl_sdl_opengl2 PUBLIC
	imgui
	${SDL2_LIBRARIES}
	${OPENGL_gl_LIBRARY}
	)

#
# example_sdl_opengl2
#

add_subdirectory(example_sdl_opengl2)
