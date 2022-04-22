# cmake for OpenCV Cookbook 3rd edition chapter 10
# your opencv/build directory should be in your system PATH

# set minimum required version for cmake
cmake_minimum_required(VERSION 3.0)

#define the project name
set(project_name "Chapter 10")

#set the project name
project("${project_name}")

set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_CXX_STANDARD 17)

#add opencv package to the project
find_package(OpenCV REQUIRED)
INCLUDE_DIRECTORIES(${OpenCV_INCLUDE_DIRS})

# add executable
add_executable( estimateF estimateF.cpp)
add_executable( robustmatching robustmatching.cpp)
add_executable( estimateH estimateH.cpp)
add_executable( matchingTarget matchingTarget.cpp)

# link libraries
target_link_libraries( estimateF ${OpenCV_LIBS})
target_link_libraries( robustmatching ${OpenCV_LIBS})
target_link_libraries( estimateH ${OpenCV_LIBS})
target_link_libraries( matchingTarget ${OpenCV_LIBS})

# copy required images to every directory with executable
SET (IMAGES ${CMAKE_SOURCE_DIR}/images/church01.jpg 
            ${CMAKE_SOURCE_DIR}/images/church02.jpg
            ${CMAKE_SOURCE_DIR}/images/church03.jpg
            ${CMAKE_SOURCE_DIR}/images/parliament1.jpg
            ${CMAKE_SOURCE_DIR}/images/parliament2.jpg
            ${CMAKE_SOURCE_DIR}/images/parliament3.jpg
            ${CMAKE_SOURCE_DIR}/images/cookbook1.bmp
            ${CMAKE_SOURCE_DIR}/images/objects.jpg)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
