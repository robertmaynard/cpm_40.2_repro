cmake_minimum_required(VERSION 3.29.0 FATAL_ERROR)

project(validate_cpm)

if(USE_CPM)
  # get cpm
  message(STATUS "CPM")
  include(${CMAKE_CURRENT_SOURCE_DIR}/get_cpm.cmake)
  CPMAddPackage(
    NAME cpm_repro
    VERSION 1
    GIT_TAG main
    SOURCE_SUBDIR cpp
    GITHUB_REPOSITORY robertmaynard/cpm_40.2_repro)
elseif(USE_FC)
  message(STATUS "FC")
  include(FetchContent)
  FetchContent_Declare(cpm_repro
    SOURCE_SUBDIR cpp
    GIT_REPOSITORY https://github.com/robertmaynard/cpm_40.2_repro.git
    GIT_TAG main )
  FetchContent_MakeAvailable(cpm_repro)
else()
  message(STATUS "FC2")
  include(FetchContent)
  FetchContent_Declare(cpm_repro SOURCE_SUBDIR;cpp;GIT_REPOSITORY;https://github.com/robertmaynard/cpm_40.2_repro.git;GIT_TAG;main )
  FetchContent_MakeAvailable(cpm_repro)
endif()


message(STATUS "cpm_repro_SOURCE_DIR: ${cpm_repro_SOURCE_DIR}")
if(NOT example_SOURCE_DIR)
  message(FATAL_ERROR "never actually call add_subdirectory on cpm_repro")
endif()
