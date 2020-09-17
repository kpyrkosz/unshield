cmake_minimum_required(VERSION 3.0)

project(libunshield)

find_package(ZLIB REQUIRED)
find_package(OpenSSL REQUIRED)

add_subdirectory(convert_utf)

set(LIBUNSHIELD_HEADES
    "internal.h"
    "libunshield.h"
    "log.h"
    "cabfile.h"
)

set(LIBUNSHIELD_SOURCES
    "bswap.c"
    "component.c"
    "directory.c"
    "file.c"
    "file_group.c"
    "helper.c"
    "libunshield.c"
    "log.c"
)

add_library(${PROJECT_NAME} STATIC ${LIBUNSHIELD_HEADES} ${LIBUNSHIELD_SOURCES})

target_link_libraries(libunshield ZLIB::ZLIB OpenSSL::Crypto convert_utf)
