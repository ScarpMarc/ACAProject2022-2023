cmake_minimum_required(VERSION 3.20)

project("ACA")

set(sources sar_utils.cpp)

add_library(ACA_LIB_BP STATIC ${sources})

target_include_directories(ACA_LIB_BP PUBLIC .)
set_property(TARGET ACA_LIB_BP PROPERTY CXX_STANDARD 17)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")