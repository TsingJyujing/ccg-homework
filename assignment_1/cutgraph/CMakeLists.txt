project(CutGraph)

find_package(OpenGL REQUIRED)
# Include MeshLib core and the 'include' of the project itsself
include_directories(
    "include"
    "${MeshLib_DIR}/core"
    "${freeglut_DIR}/include")

# Manually add the sources
# set(SOURCES_ONE ${MeshLib_DIR}/core/bmp/RgbImage.cpp)

# Also, the file(GLOB...) allows for wildcard additions
file(GLOB SRCS
    "include/*.h"
    "src/*.cpp")

# Add an executable target called MyDemo to be build from 
# the source files.
add_executable(CutGraph ${SRCS})

# Link the libraries of freeglut
target_link_libraries(CutGraph FreeGLUT::freeglut ${OPENGL_gl_LIBRARY})

# Install the executeable program in the bin folder of the
# current project directory.
install(TARGETS CutGraph DESTINATION ${CMAKE_SOURCE_DIR}/bin)
