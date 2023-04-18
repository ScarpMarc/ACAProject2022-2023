cmake_minimum_required(VERSION 3.20)

project("ACA")

set(sources src/sar_backprojection.cpp src/sar_kernel3_driver.cpp)

add_executable(BP_Ser ${sources})

target_include_directories(BP_Ser PUBLIC ./src ../lib ../../../lib /home/marco/Repos/ACAProject2022-2023/kernels/ser/bp/./../../../HLS_arbitrary_Precision_Types/include/)

target_link_libraries(BP_Ser ACA_LIBS_GLOBAL)
target_link_libraries(BP_Ser ACA_LIB_BP)

set_property(TARGET BP_Ser PROPERTY CXX_STANDARD 17)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")