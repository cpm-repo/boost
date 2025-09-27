project(boost.cpm-example-target_link_libraries CXX)

find_package(Boost REQUIRED)

add_executable(
  hello
)

target_sources(
  hello
  PRIVATE main.cpp
)

target_link_libraries(
  hello
  PRIVATE Boost::asio Boost::container
)
