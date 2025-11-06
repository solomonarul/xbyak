cmake_minimum_required(VERSION 3.10)

project(xbyak LANGUAGES CXX VERSION 7.30)

file(GLOB headers xbyak/*.h)

add_library(${PROJECT_NAME} INTERFACE)

target_include_directories(
	${PROJECT_NAME} INTERFACE
	"$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>"
)

# TODO: figure out why it crashes with any option greater than O1, this forces anything using it to compile with O1
# It crashes while freeing the code when using AutoGrow.
target_compile_options(${PROJECT_NAME} INTERFACE
    $<$<CONFIG:Release>:-O1>
)
