cmake_minimum_required(VERSION 3.20.0 FATAL_ERROR)

project(example)

if(NOT example_SOURCE_DIR STREQUAL PROJECT_SOURCE_DIR)
  message(FATAL_ERROR "
  example_SOURCE_DIR: ${example_SOURCE_DIR}
  project_SOURCE_DIR: ${project_SOURCE_DIR}
  ")
endif()

# local vs cache?
message(STATUS "CACHE{cpm_repro_SOURCE_DIR} before project: $CACHE{cpm_repro_SOURCE_DIR}")
message(STATUS "cpm_repro_SOURCE_DIR before project: ${cpm_repro_SOURCE_DIR}")
project(cpm_repro)

message(STATUS "CACHE{cpm_repro_SOURCE_DIR} after project: $CACHE{cpm_repro_SOURCE_DIR}")
message(STATUS "cpm_repro_SOURCE_DIR after project: ${cpm_repro_SOURCE_DIR}")

if(NOT cpm_repro_SOURCE_DIR STREQUAL PROJECT_SOURCE_DIR)
  message(FATAL_ERROR "
  cpm_repro_SOURCE_DIR: ${cpm_repro_SOURCE_DIR}
  PROJECT_SOURCE_DIR: ${PROJECT_SOURCE_DIR}
  example_SOURCE_DIR: ${example_SOURCE_DIR}
  ")
endif()
message(STATUS "cpm_repro_SOURCE_DIR: ${cpm_repro_SOURCE_DIR}")


