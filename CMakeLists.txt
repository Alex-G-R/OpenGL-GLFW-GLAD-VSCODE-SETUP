cmake_minimum_required(VERSION 3.10)

project(OpenGL-setup)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Set paths
set(SOURCE_DIR ${CMAKE_SOURCE_DIR}/src)
set(INCLUDE_DIR ${CMAKE_SOURCE_DIR}/include)
set(LIB_DIR ${CMAKE_SOURCE_DIR}/lib)

# Find all source files
file(GLOB_RECURSE SOURCES "${SOURCE_DIR}/*.cpp" "${SOURCE_DIR}/glad.c")

# Define executable
add_executable(OpenGL-setup ${SOURCES})

# Include directories
include_directories(${INCLUDE_DIR})

# Link libraries
link_directories(${LIB_DIR})
target_link_libraries(OpenGL-setup ${LIB_DIR}/libglfw3dll.a)
