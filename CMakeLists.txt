cmake_minimum_required(VERSION 3.0)

project(unshield VERSION 1.4)

if (MSVC)
    add_definitions(-D_CRT_SECURE_NO_WARNINGS)
    include_directories(${CMAKE_CURRENT_SOURCE_DIR}/win32_msvc)
endif ()

add_subdirectory(convert_utf)
add_subdirectory(libunshield)
add_subdirectory(unshield)
