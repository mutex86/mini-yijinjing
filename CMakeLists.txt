cmake_minimum_required(VERSION 3.17)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wno-unused -Wno-stringop-truncation")
set(CMAKE_EXPORT_COMPILE_COMMANDS ON CACHE INTERNAL "")

project(mini-yijinjing LANGUAGES C CXX)

FILE(GLOB TARGET_CPP "src/*/*.cpp")

find_package(spdlog REQUIRED)

add_executable(mini-yijinjing  main.cpp ${TARGET_CPP}) 

target_include_directories(mini-yijinjing PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include"  )
target_compile_options(mini-yijinjing PRIVATE "-std=gnu++17")
target_link_libraries(mini-yijinjing PRIVATE spdlog::spdlog)

