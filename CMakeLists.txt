cmake_minimum_required(VERSION 3.0.0)
project(MAIN)

# Set C++ standard version
add_compile_options(-std=c++23)

# Enables all warnings and treats them as errors
add_compile_options(-Wall -Wextra -Werror -Wpedantic)

# Set BINARY variable
set(BINARY ${CMAKE_PROJECT_NAME})

# Create necessary directories
file(MAKE_DIRECTORY ./bin)

# Sets the proper path for saving executables in bin folder of the project
set(EXECUTABLE_OUTPUT_PATH ../bin)


# Include source files (for tests to find them)
include_directories(src)
include_directories(header)

# Subdirectories setup
add_subdirectory(src)
add_subdirectory(header)
add_subdirectory(test)  # comment out to disable tests

# Adds a googletest library as a subdirectory,
# but given the absolute path, it can be located outside the project
# (less space used)
add_subdirectory(../lib/googletest/ ./build)  # comment out to disable tests

# Sets the variable
set(SOURCES ${SOURCES_CPP} ${SOURCES_H})

add_executable(${BINARY}_run ${SOURCES})

add_library(${BINARY}_lib STATIC ${SOURCES})

enable_testing()
