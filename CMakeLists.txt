cmake_minimum_required(VERSION 3.15) # Minimum required version of CMake
project(step2gltf LANGUAGES CXX)    # Project name and languages used
# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
# Find OpenCascade (assumes it's installed on the system)
# find_package(OpenCASCADE REQUIRED COMPONENTS TKernel TKXSBase TKSTEP TKXDESTEP TKXCAF TKService)
# Add the executable
add_executable(step2gltf main.cpp)
# Include directories from OpenCascade
target_include_directories(step2gltf PRIVATE ${OpenCASCADE_INCLUDE_DIR})
# Link libraries from OpenCascade
target_link_libraries(step2gltf PRIVATE ${OpenCASCADE_LIBRARIES})
# Set the output directory for the binary
set_target_properties(step2gltf PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin
)
