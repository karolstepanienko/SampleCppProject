# Find all source files
file(GLOB_RECURSE SOURCES_CPP LIST_DIRECTORIES false *.cpp)

# Set variable
set(SOURCES_CPP ${SOURCES_CPP} PARENT_SCOPE)
