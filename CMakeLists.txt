cmake_minimum_required(VERSION 3.24)
project(CLAY_SDL3)
add_executable(CLAY_SDL3)
target_sources(CLAY_SDL3 PRIVATE main.c)
add_subdirectory(external)

# inspired by: https://www.youtube.com/watch?v=Mi47TQ4Tsr8