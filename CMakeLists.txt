cmake_minimum_required(VERSION 3.10)

project(xbyak LANGUAGES CXX VERSION 7.30)

file(GLOB headers xbyak/*.h)

add_library(${PROJECT_NAME} INTERFACE)

target_include_directories(
	${PROJECT_NAME} INTERFACE
	"$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>"
)
