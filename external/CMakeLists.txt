add_subdirectory(SDL)
add_subdirectory(SDL_ttf)
add_subdirectory(SDL_image)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
add_library(external INTERFACE)

target_include_directories(external INTERFACE "clay")
target_link_libraries(external INTERFACE SDL3::SDL3)

add_custom_command(
        TARGET ProjectName POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory
        ${CMAKE_CURRENT_SOURCE_DIR}/assets
        ${CMAKE_CURRENT_BINARY_DIR}/assets)
#inspired by: https://github.com/libsdl-org/SDL_image/blob/main/docs/INTRO-cmake.md
#inspired by: https://discourse.libsdl.org/t/how-to-compile-a-program-that-uses-sdl-image-and-sdl-ttf/16095
