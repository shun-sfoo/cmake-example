# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.21)

# Set the project name
# the project() function, will create a variable ${PROJECT_NAME} with the value hello_cmake.  
project(hello_cmake)   

# add_executeable(hello_cmake main.cc)
add_executable(${PROJECT_NAME} main.cc)


