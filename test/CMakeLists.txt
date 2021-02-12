# Set BINARY variable
set(BINARY ${CMAKE_PROJECT_NAME}_test)

# Sets the proper path for saving executables in bin folder of the project
set(EXECUTABLE_OUTPUT_PATH ../../bin)


# Add files without folders to TEST_SOURCES
file(GLOB_RECURSE TEST_SOURCES LIST_DIRECTORIES false *.h *.cpp)

# Create executable file
add_executable(${BINARY} ${TEST_SOURCES})

add_test(TEST ${BINARY} COMMAND ${BINARY})

target_link_libraries(${BINARY} PUBLIC ${CMAKE_PROJECT_NAME}_lib gtest)