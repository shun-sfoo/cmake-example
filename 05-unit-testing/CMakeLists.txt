cmake_minimum_required(VERSION 3.20)

# Set the project name
project (google_test_example)

# GoogleTest requires at least C++11
set(CMAKE_CXX_STANDARD 11)

# compile database
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# google test
include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        e2239ee6043f73722e7aa812a459f54a28552929 # release-1.11.0
)


FetchContent_MakeAvailable(googletest)


# Add a testing executable
add_executable(unit_tests unit_tests.cc)
# add_executable(unit_main main.cc)

add_test(test_all unit_tests)
