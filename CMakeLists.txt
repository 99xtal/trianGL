cmake_minimum_required(VERSION 3.10)
project(trianGL)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(lib/glfw)

find_package(OpenGL REQUIRED)

add_executable(trianGL src/main lib/glad/src/gl.c)
include_directories(lib/glad/include)
target_link_libraries(trianGL glfw OpenGL::GL)