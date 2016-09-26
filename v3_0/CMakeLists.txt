cmake_minimum_required(VERSION 2.4)
project(blacklib)
set(CMAKE_BUILD_TYPE Release)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x -O0 -g3 -Wall -c -fmessage-length=0 -pthread -D__GXX_EXPERIMENTAL_CXX0X__ -D__GCC_HAVE_SYNC_COMPARE_AND_SWAP_1 -D__GCC_HAVE_SYNC_COMPARE_AND_SWAP_2 -D__GCC_HAVE_SYNC_COMPARE_AND_SWAP_4 -D__GCC_HAVE_SYNC_COMPARE_AND_SWAP_8")

set(CMAKE_LINK_LIBRARY_FLAG "-lpthread -L/usr/arm-linux-gnueabi/lib")

include_directories(include)

file(GLOB SOURCES "src/*.cpp")

add_library(blacklib SHARED ${SOURCES})
install(TARGETS blacklib LIBRARY DESTINATION lib)