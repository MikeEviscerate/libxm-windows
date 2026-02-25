cmake_minimum_required(VERSION 3.21)
project(xmwave LANGUAGES C)
set(CMAKE_C_STANDARD 23)
set(CMAKE_INTERPROCEDURAL_OPTIMIZATION TRUE)

option(BUILD_SHARED_LIBS "Build using shared libraries" OFF)

set(XM_VERBOSE OFF CACHE BOOL "" FORCE)
add_subdirectory(../../src xm_build)

add_executable(xmwave xmwave.c)
target_link_libraries(xmwave PRIVATE xm)

