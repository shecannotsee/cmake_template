# set cmake version
cmake_minimum_required(VERSION 3.10)
set(PROJECT_NAME "0514e860ae791ae88852c0a675e0df4a")
project(${PROJECT_NAME})

# test
message(STATUS "test start--------------------------------------------------------------------------------------------")

# set var
set(MY_VAR "Hello cmake!")
message(STATUS "MY_VAR:${MY_VAR}")
message(WARNING "warning test:MY_VAR:${MY_VAR}")

# if-elseif-else
set(ERROR_TEST OFF)
if (${ERROR_TEST} STREQUAL ON)
    message(SEND_ERROR "error")
    message(FATAL_ERROR "error")
elseif (${ERROR_TEST} STREQUAL OFF)
    message(STATUS "ERROR_TEST close: ${ERROR_TEST}")
else ()
    message(STATUS "Unknown ERROR_TEST: ${ERROR_TEST}")
endif ()

# function
function(PRINT_MESSAGE message)
    message(STATUS "[PRINT_MESSAGE] ${message}")
endfunction()
PRINT_MESSAGE(${MY_VAR})

# os
if (CMAKE_SYSTEM_NAME STREQUAL "Linux")
    PRINT_MESSAGE("os:linux")
elseif (CMAKE_SYSTEM_NAME STREQUAL "Darwin")
    PRINT_MESSAGE("os:macOS")
elseif (CMAKE_SYSTEM_NAME STREQUAL "Windows")
    PRINT_MESSAGE("os:windows")
else ()
    PRINT_MESSAGE("Unknown os")
endif ()

# compiler
if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
    PRINT_MESSAGE("compiler:gnu c++")
elseif (CMAKE_CXX_COMPILER_ID STREQUAL "Clang")
    PRINT_MESSAGE("compiler:clang c++")
elseif (CMAKE_CXX_COMPILER_ID STREQUAL "MSVC")
    PRINT_MESSAGE("compiler:msvc c++")
else ()
    PRINT_MESSAGE("compiler:Unsupported compiler")
endif ()

# get list
function(PRINT_ITEM message)
    message(STATUS "[PRINT_ITEM] ${message}")
endfunction()
set(MY_LIST 1 2 3 4 5 "-pthread")
foreach(item IN LISTS MY_LIST)
    PRINT_ITEM("item: ${item}")
endforeach()

# test sample: cmake -Dcommand_line_t2=t2 -Dcommand_line_t1=t1 ..
# change var from command line
set(command_line_t1 "file default" CACHE STRING "test var")
PRINT_ITEM("command_line:${command_line_t1}")

if(NOT DEFINED command_line_t2)
    set(command_line_t2 "file default")
endif()
PRINT_ITEM("command_line:${command_line_t2}")

message(STATUS "test done---------------------------------------------------------------------------------------------")
