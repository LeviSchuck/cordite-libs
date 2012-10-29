cmake_minimum_required(VERSION 2.8)
project(ZeroMQ)

FILE(GLOB zmq_src "src/*.cpp")
FILE(GLOB zmq_headers "src/*.hpp")
include_directories(${CMAKE_CURRENT_BINARY_DIR}/src/)

include(${CMAKE_MODULE_PATH}/config_header.cmake)
configure_file(src/platform.hpp.in src/platform.hpp)

add_library(cordite-zmq ${LIB_TYPE} ${zmq_src} ${zmq_headers})
target_link_libraries(cordite-zmq pthread)