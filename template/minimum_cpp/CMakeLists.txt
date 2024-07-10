# set cmake version
cmake_minimum_required(VERSION 3.10 FATAL_ERROR)

# set project information
set(PROJECT_NAME "a0514e860ae791ae88852c0a675e0df4a")
PROJECT(${PROJECT_NAME}
        VERSION 0.0.1
        LANGUAGES CXX
)

# set language standards
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# include template
include_directories()
# lib template
link_directories()

# add source code file
file(GLOB_RECURSE SRC "${CMAKE_SOURCE_DIR}/main.cpp")
add_executable(${PROJECT_NAME} ${SRC})

# link
target_link_libraries(${PROJECT_NAME})
