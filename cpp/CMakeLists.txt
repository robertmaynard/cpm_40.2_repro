cmake_minimum_required(VERSION 3.20.0 FATAL_ERROR)

project(example)
if(NOT example_SOURCE_DIR STREQUAL PROJECT_SOURCE_DIR)
  message(FATAL_ERROR "
  example_SOURCE_DIR: ${example_SOURCE_DIR}
  project_SOURCE_DIR: ${project_SOURCE_DIR}
  ")
endif()


project(cpm_repro)
if(NOT cpm_repro_SOURCE_DIR STREQUAL PROJECT_SOURCE_DIR)
  message(FATAL_ERROR "
  cpm_repro_SOURCE_DIR: ${cpm_repro_SOURCE_DIR}
  PROJECT_SOURCE_DIR: ${PROJECT_SOURCE_DIR}
  example_SOURCE_DIR: ${example_SOURCE_DIR}
  ")
endif()



