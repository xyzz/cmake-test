cmake_minimum_required(VERSION 3.8)
project(testy)

add_library(butterfly INTERFACE)
target_include_directories(butterfly INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/butterfly/")

add_library(apple STATIC apple.cpp)
target_link_libraries(apple butterfly)

add_executable(exe
	main.cpp
)

target_link_libraries(exe apple)
