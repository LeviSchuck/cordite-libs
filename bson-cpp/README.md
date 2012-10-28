# bson-cpp

## The standalone BSON C++ implementation.

"BSON" stands for "binary JSON" - a binary storage format that is JSON inspired.

This is the C++ implementation, developed by [http://www.10gen.com/](10gen) for
[http://www.mongodb.org/](mongodb). This distribution merely rips it out of the
mongodb repository into its own.

Other BSON implementations are available for most languages at
http://bsonspec.org.

## Status: beta

Note that this is not yet ready for production. While all the majority of the code has been thoroughly tested in the mongodb distribution, this fork is not yet proved stable.

The test application no longer has build code set up, because of issues with linking different std libs on mac.

The current state is unknown, though it builds on mac and linux.

## Building

The build system here uses CMake. 

    mkdir build
    cd build
    cmake ..
    make


## Installing

To install the library and headers in /usr/local, just run:

    make install

## Usage

You want to link against the library, and then:

    #include <bson/bson.h>

Check out the headers, particularly bson.h. The project is not fully well setup
though, so you may have to include other headers for now.

## License
All files in the src directory, for the library, are Apache 2.0 licensed.

All files but md5.c/h in the lib directory are Apache 2.0 licensed. 
lib/md5.* are zlib licensed.

The files in test are GNU AFFERO GENERAL PUBLIC LICENSE VERSION 3


