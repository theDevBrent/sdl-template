set(BUILD_SHARED_LIBS OFF CACHE BOOL "Build shared libraries" FORCE)

#sdl
add_subdirectory(sdl)
target_link_libraries(main SDL2::SDL2main SDL2::SDL2-static)

#sdl image
add_subdirectory(sdl-image)
target_link_libraries(main SDL2_image::SDL2_image-static)

#sdl ttf
set( SDL2TTF_SAMPLES OFF CACHE BOOL "" FORCE )
set( SDL2TTF_INSTALL OFF CACHE BOOL "" FORCE )
set( SDL2TTF_VENDORED ON CACHE BOOL "" FORCE )
set( SDL2TTF_HARFBUZZ ON CACHE BOOL "" FORCE )
add_subdirectory(sdl-ttf)
target_link_libraries(main SDL2_ttf::SDL2_ttf-static)

#sdl mixer
set( SDL2MIXER_SAMPLES OFF CACHE BOOL "" FORCE )
set( SDL2MIXER_INSTALL OFF CACHE BOOL "" FORCE )
set( SDL2MIXER_VENDORED ON CACHE BOOL "" FORCE )
set( SDL2MIXER_DEPS_SHARED OFF CACHE BOOL "" FORCE )
set( SDL2MIXER_FLAC OFF CACHE BOOL "" FORCE )
set( SDL2MIXER_MOD OFF CACHE BOOL "" FORCE )
set( SDL2MIXER_MP3 OFF CACHE BOOL "" FORCE )
set( SDL2MIXER_MIDI OFF CACHE BOOL "" FORCE )
set( SDL2MIXER_OPUS OFF CACHE BOOL "" FORCE )
add_subdirectory(sdl-mixer)
target_link_libraries(main SDL2_mixer::SDL2_mixer-static)

#glm
target_include_directories(main SYSTEM PRIVATE "glm")
