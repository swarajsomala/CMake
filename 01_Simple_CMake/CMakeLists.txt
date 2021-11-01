# CMake Version
cmake_minimum_required(VERSION 3.12)
project(sample VERSION 1.0.0 LANGUAGES CXX)
set(EXE_NAME ${PROJECT_NAME})
# Set the default build type
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Debug" CACHE STRING "Choose the type of build, one of: Debug, Release, RelWithDebInfo, MinSizeRel" FORCE)
endif()
# Specify the C++ Standard Globally and Consistently
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(cpp_src_files ${PROJECT_SOURCE_DIR}/src/main.cpp 
                  ${PROJECT_SOURCE_DIR}/src/sample.cpp
   )
add_executable(${EXE_NAME} ${cpp_src_files})
target_include_directories(${EXE_NAME}
PUBLIC
    ${PROJECT_SOURCE_DIR}/inc
)
