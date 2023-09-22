cmake_minimum_required (VERSION 2.8)
project(demo1_glfw)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)



add_executable(gapp main.c)
target_link_libraries(gapp glfw GLU GL pthread Xrandr Xi dl Xinerama rt dl X11)