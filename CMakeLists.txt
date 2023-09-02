# The minimum version of CMake required
cmake_minimum_required(VERSION 3.20)

# override some default CMake variables
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Set the name of our project
project(CppSDLTemplate CXX)

# Name of our executable
add_executable(main)
set_target_properties(main PROPERTIES OUTPUT_NAME ${CMAKE_PROJECT_NAME})
# Copy our assets folder to the build folder
add_custom_command(TARGET main POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy_directory
    ${CMAKE_SOURCE_DIR}/assets
	$<CONFIG>/assets
)

# Add our src and external directories
add_subdirectory("src")
add_subdirectory("external")
