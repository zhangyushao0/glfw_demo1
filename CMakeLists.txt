cmake_minimum_required(VERSION 3.10)
project(demo1_glfw)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

add_executable(myapp src/main.cpp)
include_directories(myapp PRIVATE include)

# OpenGL
find_package(OpenGL REQUIRED)
target_link_libraries(myapp PRIVATE OpenGL::GL)

# GLFW
add_subdirectory(external/glfw)
target_link_libraries(myapp PRIVATE glfw)
include_directories(myapp PRIVATE external/glfw/include)

# GLEW
add_subdirectory(external/glew-cmake)
target_link_libraries(myapp PRIVATE libglew_static)
include_directories(myapp PRIVATE external/glew-cmake/include)

# GLM
add_subdirectory(external/glm)
target_link_libraries(myapp PRIVATE glm)
include_directories(myapp PRIVATE external/glm)
