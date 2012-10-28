cmake_minimum_required(VERSION 2.8)
OPTION(USE_CXX_11 "Use C++11" ON)
if(USE_CXX_11)
if (APPLE)
	set(CMAKE_XCODE_ATTRIBUTE_GCC_VERSION "com.apple.compilers.llvm.clang.1_0")
	set(CMAKE_XCODE_ATTRIBUTE_CLANG_CXX_LANGUAGE_STANDARD "c++11")
	set(CMAKE_XCODE_ATTRIBUTE_CLANG_CXX_LIBRARY "libc++")
	
	#these have absolutely no effect :(
	if (CMAKE_COMPILER_IS_GNUCXX OR CMAKE_COMPILER_IS_GNUCC)
		message(FATAL_ERROR "You need to use clang on Apple!
		use CC=clang CXX=clang++ cmake path/to/project")
	endif()
	
	SET(CMAKE_CXX_FLAGS "-std=c++11 -stdlib=libc++")
endif ()
if (CMAKE_COMPILER_IS_GNUCXX OR CMAKE_COMPILER_IS_GNUCC)
  set ( CMAKE_CXX_FLAGS "-std=c++0x")
  #set ( CMAKE_CXX_FLAGS_DEBUG "")
  #set ( CMAKE_CXX_FLAGS_RELEASE  "" )
endif ()
endif(USE_CXX_11)

add_subdirectory(google)