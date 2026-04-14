cmake_minimum_required(VERSION 4.1.1)

project(Temp LANGUAGES CXX)

add_executable(main "Main.cpp")
target_compile_features(main PRIVATE cxx_std_23)
if (CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    target_compile_options(main PRIVATE "-fexperimental-library")
endif()
