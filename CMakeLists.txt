cmake_minimum_required(VERSION 3.8)
project(testy)

add_library(butterfly INTERFACE)
target_include_directories(butterfly INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/butterfly/")

add_library(apple OBJECT apple.cpp)

add_library(big $<TARGET_OBJECTS:apple>)
target_link_libraries(big butterfly)

add_executable(exe
	main.cpp
)

target_link_libraries(exe big)
