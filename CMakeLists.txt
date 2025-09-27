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
)
