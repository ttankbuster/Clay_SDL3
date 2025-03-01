cmake_minimum_required(VERSION 3.24)
project(CLAY_SDL3)
add_executable(CLAY_SDL3)
target_sources(CLAY_SDL3 PRIVATE main.c)
add_subdirectory(external)
target_link_libraries(CLAY_SDL3 PRIVATE external)
add_custom_command(
        TARGET CLAY_SDL3 POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory
        ${CMAKE_CURRENT_SOURCE_DIR}/assets
        ${CMAKE_CURRENT_BINARY_DIR}/assets)
# inspired by: https://www.youtube.com/watch?v=Mi47TQ4Tsr8