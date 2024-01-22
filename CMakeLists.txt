#====================================================================================================
# This CMake Project defines the build for the GA1 AI Lookup Utility
#====================================================================================================

#====================================================================================================
# CMake Version and Policies
#
# Defines the minimum version of CMake for this project and lists the policies that we've commited
# to.
#====================================================================================================
cmake_minimum_required(VERSION 3.18)

project(dmrc_fma)

option(DMRC_FMA_ENABLE_TESTING ${PROJECT_IS_TOP_LEVEL})
option(DMRC_FMA_BUILD_EXAMPLES ${PROJECT_IS_TOP_LEVEL})

add_subdirectory(src)

if(DMRC_FMA_ENABLE_TESTING)
    include(CTest)
    add_subdirectory(tests)
endif()

if(DMRC_FMA_BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()