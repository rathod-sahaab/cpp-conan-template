cmake_minimum_required(VERSION 3.10)

set(PROJECT_NAME "default") # CUSTOMISE: your project name
set(PROJECT_VERSION 0.1.0) # CUSTOMISE: project version
set(CMAKE_CXX_STANDARD 17) # CUSTOMISE: standard

project(${PROJECT_NAME} VERSION ${VERSION})


include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)  # Includes the contents of the conanbuildinfo.cmake file.
conan_basic_setup()  # Prepares the CMakeList.txt for Conan.

# $source_files is a space-delimited list of filenames.
add_executable(${PROJECT_NAME} src/main.cpp)  # Specifies the executable to build.
target_link_libraries(${PROJECT_NAME} ${CONAN_LIBS})  # Specifies what libraries to link, using Conan.
