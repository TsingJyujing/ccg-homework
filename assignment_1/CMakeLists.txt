cmake_minimum_required(VERSION 3.6)

# Name the project
project(CCGHomework)

# Find MeshLib
find_package(MeshLib REQUIRED
             HINTS "${CMAKE_SOURCE_DIR}/3rdparty")
if (NOT MeshLib_FOUND)
    message(FATAL_ERROR "MeshLib Not Found!")
endif (NOT MeshLib_FOUND)

# Find freeglut
find_package(freeglut REQUIRED)
if (NOT freeglut_FOUND)
    message(FATAL_ERROR "freeglut Not Found!")
else()
    message(STATUS "freeglut library status:")
    message(STATUS "    config: ${freeglut_DIR}")
    message(STATUS "    version: ${freeglut_VERSION}")
    message(STATUS "    libraries: ${freeglut_LIBS}")
    message(STATUS "    include path: ${freeglut_INCLUDE_DIRS}")
endif (NOT freeglut_FOUND)


add_subdirectory("cutgraph")

