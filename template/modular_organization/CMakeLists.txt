cmake_minimum_required(VERSION 3.10 FATAL_ERROR)
########################################################################################################################
# Project Settings                                                                                                     #
########################################################################################################################
set(project_name "a0514e860ae791ae88852c0a675e0df4a")
PROJECT(${project_name} VERSION 0.0.1 LANGUAGES CXX)

if (NOT DEFINED project_type)
    # project_type: [library] or [application]
    set(project_type "library")
endif ()

########################################################################################################################
# include                                                                                                              #
########################################################################################################################
include(${CMAKE_SOURCE_DIR}/cmake/config.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/compilation_options.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/external_settings.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/import_third_party.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/target_src.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/target_test.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/target_application.cmake)
include(${CMAKE_SOURCE_DIR}/cmake/install.cmake)
