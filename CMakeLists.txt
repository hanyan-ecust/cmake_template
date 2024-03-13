cmake_minimum_required(VERSION 3.17)
project(Template)

set(CMAKE_C_STANDARD 11)

# set include and lib path
include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)
add_subdirectory(src)