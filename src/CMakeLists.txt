# Common information
cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(BA-Prog LANGUAGES CXX)


# include sub-projects
add_subdirectory(${CMAKE_SOURCE_DIR}/socket-lib)
add_subdirectory(${CMAKE_SOURCE_DIR}/networker)
add_subdirectory(${CMAKE_SOURCE_DIR}/external/gtest)



# set variables

# root folder for external libs
set(EXT_PROJECTS_DIR ${CMAKE_SOURCE_DIR}/external)