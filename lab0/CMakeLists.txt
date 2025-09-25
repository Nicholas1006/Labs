cmake_minimum_required(VERSION 3.1)
project(lab0)

find_package(OpenGL REQUIRED)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")

add_subdirectory(external)

include_directories(
	external/glfw-3.1.2/include/
	external/glm-0.9.7.1/
	external/glad-opengl-3.3/include/
	lab0/
)

add_executable(lab0_window
	lab0/lab0_window.cpp
)
target_link_libraries(lab0_window
	${OPENGL_LIBRARY}
	glfw
)

add_executable(lab0_triangle
	lab0/lab0_triangle.cpp
)
target_link_libraries(lab0_triangle
	${OPENGL_LIBRARY}
	glfw
	glad
)
