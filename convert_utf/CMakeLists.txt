cmake_minimum_required(VERSION 3.0)

project(convert_utf)

set(LIBCONVERT_UTF_HEADES
    "ConvertUTF.h"
)

set(LIBCONVERT_UTF_SOURCES
    "ConvertUTF.c"
)

add_library(${PROJECT_NAME} STATIC ${LIBCONVERT_UTF_HEADES} ${LIBCONVERT_UTF_SOURCES})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
