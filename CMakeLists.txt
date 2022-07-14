cmake_minimum_required(VERSION 3.7)
project(matrix)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED YES)   # See below (1)
include_directories(${PROJECT_BINARY_DIR}/Include /opt/homebrew/Cellar/gsl)

set(SOURCE_FILES main.cpp)
add_executable(matrix ${SOURCE_FILES})

find_package(GSL REQUIRED)
include_directories(/opt/homebrew/Cellar/gsl)
target_link_libraries(bigkernel GSL::gsl GSL::gslcblas)

# find_library (GSL_LIBRARY gsl /opt/homebrew/Cellar/gsl/)
# target_link_libraries(matrix GSL::gsl GSL::gslcblas)
# find_package(GSL REQUIRED)    # See below (2)
