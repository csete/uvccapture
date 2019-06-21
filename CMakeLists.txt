cmake_minimum_required (VERSION 2.8.10.2)
project(uvccapture)

include_directories(BEFORE ${CMAKE_INCLUDE_PATH})

link_directories(BEFORE ${CMAKE_LIBRARY_PATH})

if(NOT DEFINED CMAKE_BUILD_TYPE)
	set(CMAKE_BUILD_TYPE RELEASE)
endif(NOT DEFINED CMAKE_BUILD_TYPE)

set(CMAKE_CXX_FLAGS_RELEASE "-O3 -std=c++11")
set(CMAKE_CXX_FLAGS_DEBUG   "-O0 -ggdb -g3 -std=c++11")
set(CMAKE_C_FLAGS_RELEASE   "-O3 -std=c11")
set(CMAKE_C_FLAGS_DEBUG     "-O0 -ggdb -g3 -std=c11")

add_executable(uvccapture uvccapture.c v4l2uvc.c)
install(TARGETS uvccapture DESTINATION bin)


