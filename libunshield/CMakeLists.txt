cmake_minimum_required(VERSION 3.0)

project(libunshield)

find_package(ZLIB REQUIRED)
find_package(OpenSSL REQUIRED)

set(LIBUNSHIELD_HEADES
    inc/internal.h
    inc/libunshield.h
    inc/log.h
    inc/cabfile.h
)

set(LIBUNSHIELD_SOURCES
    src/bswap.c
    src/component.c
    src/directory.c
    src/file.c
    src/file_group.c
    src/helper.c
    src/libunshield.c
    src/log.c
)

add_library(${PROJECT_NAME} STATIC ${LIBUNSHIELD_HEADES} ${LIBUNSHIELD_SOURCES})
target_link_libraries(${PROJECT_NAME} PRIVATE ZLIB::ZLIB OpenSSL::Crypto convert_utf)
target_include_directories(${PROJECT_NAME} PUBLIC inc)
