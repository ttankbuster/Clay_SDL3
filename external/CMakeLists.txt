add_subdirectory(SDL)
set(SDLTTF_VENDORED ON)
add_subdirectory(SDL_ttf)
add_subdirectory(SDL_image)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
add_library(external INTERFACE)

target_include_directories(external INTERFACE "clay")
target_link_libraries(external INTERFACE SDL3::SDL3)

#inspired by: https://github.com/libsdl-org/SDL_image/blob/main/docs/INTRO-cmake.md
#inspired by: https://discourse.libsdl.org/t/how-to-compile-a-program-that-uses-sdl-image-and-sdl-ttf/16095
