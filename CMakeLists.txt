cmake_minimum_required(VERSION 3.22)

project(libtinyfiledialogs C)

add_library(${PROJECT_NAME} STATIC src/tinyfiledialogs.c include/tinyfiledialogs.h)
target_include_directories(${PROJECT_NAME} PUBLIC include)

option(TINYFILEDIALOGS_ALLOW_POINTER_BOOL_CONVERSION OFF)
if (TINYFILEDIALOGS_ALLOW_POINTER_BOOL_CONVERSION)
    target_compile_options(${PROJECT_NAME} PRIVATE -Wno-pointer-bool-conversion)
endif ()
