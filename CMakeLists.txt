cmake_minimum_required(VERSION 3.11)
project(simple-mtpfs)

include_directories(.)

add_definitions(-D_FILE_OFFSET_BITS=64 -DFUSE_USE_VERSION=26)

add_subdirectory(src)
add_subdirectory(man)
