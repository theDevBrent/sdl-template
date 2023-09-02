set(BUILD_SHARED_LIBS OFF CACHE BOOL "Build shared libraries" FORCE)

#sdl
add_subdirectory(sdl)
target_link_libraries(main SDL2::SDL2main SDL2::SDL2-static)

#sdl image
add_subdirectory(sdl-image)
target_link_libraries(main SDL2_image::SDL2_image-static)

#sdl ttf
add_subdirectory(sdl-ttf)
target_link_libraries(main SDL2_ttf::SDL2_ttf-static)

#sdl mixer
add_subdirectory(sdl-mixer)
target_link_libraries(main SDL2_mixer::SDL2_mixer-static)

#glm
target_include_directories(main SYSTEM PRIVATE "glm")