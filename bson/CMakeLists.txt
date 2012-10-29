cmake_minimum_required(VERSION 2.8)
project(bson-cpp)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/inc)


set(BSON_HEADERS
	inc/bson-inl.h
	inc/bson.h
	inc/bsonassert.h
	inc/bsonelement.h
	inc/bsonmisc.h
	inc/bsonobj.h
	inc/bsonobjbuilder.h
	inc/bsonobjiterator.h
	inc/bsontypes.h
	inc/inline_decls.h
	inc/oid.h
	inc/ordering.h
	inc/stringdata.h
	inc/builder.h
	inc/embedded_builder.h
	inc/hex.h
	inc/misc.h
	inc/noncopyable.h
	inc/optime.h
)
set(BSON_SOURCE
	src/bsonobj.cpp
        src/oid.cpp
        lib/base64.cpp
        lib/md5.c
        lib/nonce.cpp
)

add_library(cordite-bsoncpp ${LIB_TYPE} ${BSON_SOURCE} ${BSON_HEADERS})


install(TARGETS cordite-bsoncpp
	LIBRARY DESTINATION lib
	ARCHIVE DESTINATION lib)
install(DIRECTORY inc/ DESTINATION include/bson
	FILES_MATCHING PATTERN "*.h"
)
