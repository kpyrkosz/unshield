cmake_minimum_required(VERSION 3.0)

project(unshield)

add_executable(${PROJECT_NAME} unshield.c)
target_link_libraries(${PROJECT_NAME} PRIVATE libunshield)

add_executable(unshield-deobfuscate unshield-deobfuscate.c)
target_link_libraries(unshield-deobfuscate PRIVATE libunshield)
