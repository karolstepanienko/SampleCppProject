# Find all header files
file(GLOB_RECURSE SOURCES_H LIST_DIRECTORIES false *.h)

# Set variable
set(SOURCES_H ${SOURCES_H} PARENT_SCOPE)
