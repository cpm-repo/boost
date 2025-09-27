cmake_minimum_required(VERSION 3.14)

project(boost.cpm)

if(PROJECT_IS_TOP_LEVEL)
  file(DOWNLOAD https://github.com/cpm-cmake/CPM.cmake/releases/latest/download/CPM.cmake
       ${CMAKE_CURRENT_BINARY_DIR}/cmake/CPM.cmake
  )
  include(${CMAKE_CURRENT_BINARY_DIR}/cmake/CPM.cmake)
endif()

get_property(
  CPM_INITIALIZED GLOBAL
  PROPERTY CPM_INITIALIZED
  SET
)

if(NOT CPM_INITIALIZED)
  message(FATAL "You should include CPM.cmake frist")
endif()

CPMAddPackage(
  NAME Boost
  VERSION 1.89.0
  URL https://github.com/boostorg/boost/releases/download/boost-1.89.0/boost-1.89.0-cmake.tar.xz
  EXCLUDE_FROM_ALL YES
  SYSTEM NO
)

if(NOT PROJECT_IS_TOP_LEVEL)
  return()
endif()

add_subdirectory(examples)
