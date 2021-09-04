# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.21)

# Set the project name
project (hello_headers)

# Create a sources variable with a link to all cpp files to compile
# For modern CMake it is NOT recommended to use a variable for sources.
# Instead it is typical to directly declare the sources in the add_xxx function
set(SOURCES
    src/Hello.cc
    src/main.cc
)

# An alternative to setting specific file names in the SOURCES variable is
# to use a GLOB command to find files using wildcard pattern matching.
# file(GLOB SOURCES "src/*.cpp")

# Add an executable with the above sources
add_executable(hello_headers ${SOURCES})

# Set the directories that should be included in the build command for this target
# when running g++ these will be included as -I/directory/path/
target_include_directories(hello_headers
    PRIVATE 
        ${PROJECT_SOURCE_DIR}/include
)
