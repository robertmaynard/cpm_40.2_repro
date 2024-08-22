cmake_minimum_required(VERSION 3.20.0 FATAL_ERROR)

project(validate_cpm)

# get cpm
include(${CMAKE_CURRENT_SOURCE_DIR}/get_cpm.cmake)

CPMAddPackage(
  NAME cpm_repro
  VERSION 1
  GIT_TAG main
  GITHUB_REPOSITORY robertmaynard/cpm_40.2_repro
  SOURCE_SUBDIR cpp
)



