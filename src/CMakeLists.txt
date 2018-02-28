# Common information
cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(BA-Prog LANGUAGES CXX)

#enable command line arguments
option(COVERAGE "run the coverage analysis" OFF)

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
if(COVERAGE)
        include( ${script_dir}/CodeCoverage.cmake )

        APPEND_COVERAGE_COMPILER_FLAGS()

        set(COVERAGE_EXCLUDES '${ext_dir}/*'  )

        # add way to run all unittests with one target
        SETUP_TARGET_FOR_COVERAGE(
                NAME coverage_runner
                EXECUTABLE unit_TCP -j ${PROCESSOR_COUNT}
                DEPENDENCIES unit_TCP
        )
endif(COVERAGE)