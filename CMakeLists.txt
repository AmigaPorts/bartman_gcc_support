cmake_minimum_required(VERSION 3.14.0)
project(bartman_gcc_support
	LANGUAGES C ASM
	DESCRIPTION "Bartman GCC compiler support library"
	HOMEPAGE_URL "https://github.com/AmigaPorts/bartman_gcc_support"
)

file(GLOB SOURCES src/*.c src/*.s include/bartman/*.h)
add_library(bartman_gcc_support OBJECT ${SOURCES})
target_include_directories(bartman_gcc_support PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)
target_include_directories(bartman_gcc_support PRIVATE ${CMAKE_CURRENT_LIST_DIR}/include/bartman)
