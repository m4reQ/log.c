cmake_minimum_required(VERSION 3.22)

option(LOG_USE_COLOR "If present library will use colors while logging" OFF)

project(logc)

add_library(logc STATIC "src/log.c")
target_include_directories(logc PUBLIC "src")

if(${LOG_USE_COLOR})
	target_compile_definitions(logc PRIVATE LOG_USE_COLOR)
endif()