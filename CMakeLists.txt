cmake_minimum_required(VERSION 3.24)

project(glfw_task)

set(CMAKE_CXX_STANDARD_REQUIRED 20)

find_package(OpenGL REQUIRED)

include(FetchContent)
FetchContent_Declare(
    glfw
    GIT_REPOSITORY https://github.com/glfw/glfw
    GIT_TAG 3.3.8
)
FetchContent_MakeAvailable(glfw)

add_executable(glfw_task main.cpp ./glad/glad.c)
target_include_directories(glfw_task PRIVATE ${GLFW_SOURCE_DIR}/include ./glad)
target_link_libraries(glfw_task PRIVATE glfw OpenGL::GL)
