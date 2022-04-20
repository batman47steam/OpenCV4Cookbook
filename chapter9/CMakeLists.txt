# cmake for OpenCV Cookbook 3rd edition chapter 09
# your opencv/build directory should be in your system PATH

# set minimum required version for cmake
cmake_minimum_required(VERSION 3.0)

# define the project name
set(project_name "Chapter 9")

# set the project name
project("${project_name}")

# 设置指定的c++编译器版本是必须的，如果不设置，或者为OFF，则指定版本不可用时，回使用上一版本
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 指定为c++17
set(CMAKE_CXX_STANDARD 17)

# add opencv package to the project
find_package(OpenCV REQUIRED)
INCLUDE_DIRECTORIES(${OpenCV_INCLUDE_DIRS})

message(STATUS "OpenCV library status:")
message(STATUS "version: ${OpenCV_VERSION}")
message(STATUS "libraries: ${OpenCV_LIBS}")
message(STATUS "include path: ${OpenCV_INCLUDE_DIRS}")

# add executable
add_executable( patches patches.cpp)
add_executable( matcher matcher.cpp)
add_executable( binaryDescriptors binaryDescriptors.cpp)

# link libraries
target_link_libraries( patches ${OpenCV_LIBS})
target_link_libraries( matcher ${OpenCV_LIBS})
target_link_libraries( binaryDescriptors ${OpenCV_LIBS})

# copy required images to every directory with executable
SET (IMAGES ${CMAKE_SOURCE_DIR}/images/church01.jpg 
            ${CMAKE_SOURCE_DIR}/images/church02.jpg
            ${CMAKE_SOURCE_DIR}/images/church03.jpg)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
