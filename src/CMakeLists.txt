cmake_minimum_required (VERSION 2.6)
project (RedSpider)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x -O3")
if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
    add_definitions(-stdlib=libc++)
endif()

set(CMAKE_INSTALL_PREFIX ..)

include_directories("../include")

add_executable(gameofspiders rsGameOfLife.cpp rsTerminal.cpp)

install(TARGETS gameofspiders DESTINATION bin)
