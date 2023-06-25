cmake_minimum_required(VERSION 3.24)
project(opengl)

set(CMAKE_CXX_STANDARD 17)





# Define the executable
add_executable(opengl main.cpp glad.c)


# We need a CMAKE_DIR with some code to find external dependencies
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")


add_subdirectory(glfw-3.3.8)
target_link_libraries(opengl glfw)
find_package(OpenGL REQUIRED)
target_link_libraries(opengl OpenGL::GL)



