cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

add_library(iconv STATIC lib/iconv.c libcharset/lib/localcharset.c lib/relocatable.c)

target_include_directories(iconv PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>/include)

target_include_directories(iconv PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>/lib)

