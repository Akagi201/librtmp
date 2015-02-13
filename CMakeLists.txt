#
# @file CMakeLists.txt
# @author Akagi201
# @date 2015/02/13
#

cmake_minimum_required(VERSION 2.8.4)
project(librtmp)

set(LIBRTMP_HEADERS
amf.h
dh.h
handshake.h
log.h
rtmp_sys.h
bytes.h
dhgroups.h
http.h
rtmp.h
)

set (LIBRTMP_SOURCES
amf.c
hashswf.c
log.c
parseurl.c
rtmp.c
)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wuninitialized -Wno-deprecated -Wno-unused-const-variable")

add_library(librtmp_static STATIC ${LIBRTMP_SOURCES} ${LIBRTMP_HEADERS})

set_target_properties(librtmp_static PROPERTIES OUTPUT_NAME "rtmp")
