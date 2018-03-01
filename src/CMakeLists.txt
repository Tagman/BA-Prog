# Common information
cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(BA-Prog LANGUAGES CXX)

#enable command line arguments
option(COVERAGE "run the coverage analysis" OFF)
option(COV_OUTPUT "enable targets for html, or xml output. Has additional dependecies" OFF)

set(ext_dir ${CMAKE_SOURCE_DIR}/external )
set(script_dir ${CMAKE_SOURCE_DIR}/../scripts )
# add external tools
#add_subdirectory(${CMAKE_SOURCE_DIR}/external/gtest)


# include sub-projects
add_subdirectory(${CMAKE_SOURCE_DIR}/socket-lib)
add_subdirectory(${CMAKE_SOURCE_DIR}/networker)




# set variables

# root folder for external libs


# setup coverage for whole project
