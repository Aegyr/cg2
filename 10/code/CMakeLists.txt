# Name the project you can choose any name you want here
PROJECT(Exercise10) 

# Check requirements
CMAKE_MINIMUM_REQUIRED(VERSION 2.6.0)

# set the compiler flags
SET(CMAKE_BUILD_TYPE debug)
SET(CMAKE_CXX_FLAGS "-Wall")

# Add path to additional packages (makes it easier to include common libraries)
set(CMAKE_MODULE_PATH ${Exercise10_SOURCE_DIR}/CMakeModules/)

# Define where your executables should be put
set(EXECUTABLE_OUTPUT_PATH ${Exercise10_BINARY_DIR})

# Add required packages (e.g. libraries)
FIND_PACKAGE(OpenGL 3.3 REQUIRED)
FIND_PACKAGE(GLEW REQUIRED)
FIND_PACKAGE(GLUT REQUIRED)
#FIND_PACKAGE(OpenCV REQUIRED)

# Set include directories containing used header files
INCLUDE_DIRECTORIES(
  ${Exercise10_SOURCE_DIR}/include
  /usr/include
)

# Set link directories for addiontional libraries
LINK_DIRECTORIES(
  ${Exercise10_SOURCE_DIR}/lib
  /usr/lib
)

# Tell CMake to process the sub-directories
ADD_SUBDIRECTORY(src)
