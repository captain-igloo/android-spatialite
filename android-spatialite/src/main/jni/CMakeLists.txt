cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

set(lib_src_DIR ${CMAKE_CURRENT_SOURCE_DIR})

set(lib_build_DIR $ENV{HOME}/tmp/${ANDROID_ABI})
file(MAKE_DIRECTORY ${lib_build_DIR})

add_subdirectory(${lib_src_DIR}/sqlite3 ${lib_build_DIR}/sqlite3)
add_subdirectory(${lib_src_DIR}/proj ${lib_build_DIR}/proj)
add_subdirectory(${lib_src_DIR}/iconv ${lib_build_DIR}/iconv)
add_subdirectory(${lib_src_DIR}/geos ${lib_build_DIR}/geos)
add_subdirectory(${lib_src_DIR}/rttopo ${lib_build_DIR}/rttopo)
add_subdirectory(${lib_src_DIR}/libspatialite ${lib_build_DIR}/libspatialite)
