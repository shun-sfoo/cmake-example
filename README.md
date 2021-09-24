# cmake-example

learn cmake

1. Declare a target
2. Declare target's traits
3. It's all about targets

# generat compile command json file

`cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=ON .`

# Have cmake create a compile database

`set(CMAKE_EXPORT_COMPILE_COMMANDS ON)`

## Referencing Sub-Project Directories

| Variable             | Info                                                                                                                                                              |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `PROJECT_NAME`       | The name of the project set by `the current project()`.                                                                                                           |
| `CMAKE_PROJECT_NAME` | the name of the first project set by the `project()` command, i.e. the top level project.                                                                         |
| `PROJECT_SOURCE_DIR` | The source director of the current project.                                                                                                                       |
| `PROJECT_BINARY_DIR` | The build directory for the current project.                                                                                                                      |
| `name_SOURCE_DIR`    | source directory of the project called "name". source directories created would be `sublibrary1_SOURCE_DIR`, `sublibrary2_SOURCE_DIR`, and `subbinary_SOURCE_DIR` |
| `name_BINARY_DIR`    | binary directory of the project called "name". binary directories created would be `sublibrary1_BINARY_DIR`, `sublibrary2_BINARY_DIR`, and `subbinary_BINARY_DIR` |

## Header only Libraries

If you have a library that is created as a header only library, cmake supports the INTERFACE target to allow creating a target without any build output.
More details can be found from [here](https://cmake.org/cmake/help/v3.4/command/add_library.html#interface-libraries)

`add_library(${PROJECT_NAME} INTERFACE)`

## static analyzer

### clang-analyzer

`scan-build cmake .` and `scan-build make`
`scan-view`
