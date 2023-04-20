cmake_minimum_required(VERSION 3.20)

project("ACA")

set(sources octave/octave.cpp timing/timer.cpp xmem/xmalloc.cpp)

add_library(ACA_LIBS_GLOBAL STATIC ${sources})

target_include_directories(ACA_LIBS_GLOBAL PUBLIC octave timing xmem)

set_property(TARGET ACA_LIBS_GLOBAL PROPERTY CXX_STANDARD 17)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")