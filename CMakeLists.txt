cmake_minimum_required(VERSION 4.1.1)

project(Zippy
  LANGUAGES CXX
  VERSION 0.1.0
)

add_subdirectory(lib)

add_executable(main "Main.cpp")
target_compile_features(main PRIVATE cxx_std_23)

target_link_libraries(main PRIVATE zippy)
