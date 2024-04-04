cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

add_library(rttopo STATIC src/box2d.c
                          src/bytebuffer.c
                          src/g_box.c
                          src/g_serialized.c
                          src/g_util.c
                          src/measures.c
                          src/measures3d.c
                          src/ptarray.c
                          src/rtalgorithm.c
                          src/rtcircstring.c
                          src/rtcollection.c
                          src/rtcompound.c
                          src/rtcurvepoly.c
                          src/rtgeodetic.c
                          src/rtgeom.c
                          src/rtgeom_api.c
                          src/rtgeom_debug.c
                          src/rtgeom_geos.c
                          src/rtgeom_geos_clean.c
                          src/rtgeom_geos_node.c
                          src/rtgeom_geos_split.c
                          src/rtgeom_topo.c
                          src/rthomogenize.c
                          src/rtin_geojson.c
                          src/rtin_twkb.c
                          src/rtin_wkb.c
                          src/rtiterator.c
                          src/rtline.c
                          src/rtlinearreferencing.c
                          src/rtmcurve.c
                          src/rtmline.c
                          src/rtmpoint.c
                          src/rtmpoly.c
                          src/rtmsurface.c
                          src/rtout_encoded_polyline.c
                          src/rtout_geojson.c
                          src/rtout_gml.c
                          src/rtout_kml.c
                          src/rtout_svg.c
                          src/rtout_twkb.c
                          src/rtout_wkb.c
                          src/rtout_wkt.c
                          src/rtout_x3d.c
                          src/rtpoint.c
                          src/rtpoly.c
                          src/rtprint.c
                          src/rtpsurface.c
                          src/rtspheroid.c
                          src/rtstroke.c
                          src/rttin.c
                          src/rttree.c
                          src/rttriangle.c
                          src/rtt_tpsnap.c
                          src/rtutil.c
                          src/stringbuffer.c
                          src/varint.c)

target_include_directories(rttopo PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>/src)

target_include_directories(rttopo PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>/headers)