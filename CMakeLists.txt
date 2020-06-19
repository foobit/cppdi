cmake_minimum_required(VERSION 3.8)
project(cppdi)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(gravity)

add_executable(cppdi src/main.cpp)
target_link_libraries(cppdi PUBLIC gravityapi_s)
