cmake_minimum_required(VERSION 2.8)
project(demo1_glfw)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

add_subdirectory(external/glfw)

add_executable(gapp src/main.cpp)

target_link_libraries(gapp glfw)
find_package(OpenGL REQUIRED)
target_link_libraries(gapp OpenGL::GL)

include_directories(include/)