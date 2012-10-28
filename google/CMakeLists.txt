include_directories(${CMAKE_CURRENT_BIRNARY_DIR})
include(${CMAKE_MODULE_PATH}/config_header.cmake)
configure_file(config.h.in config.h)


add_subdirectory(protobuf)
