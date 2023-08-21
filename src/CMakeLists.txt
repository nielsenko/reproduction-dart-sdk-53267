# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

project(bomb_library VERSION 0.0.1 LANGUAGES CXX)

add_library(bomb SHARED
  "bomb.cpp"
)

set_target_properties(bomb PROPERTIES
  CXX_STANDARD 17
  PUBLIC_HEADER bomb.h
  OUTPUT_NAME "bomb"
)

target_compile_definitions(bomb PUBLIC DART_SHARED_LIB)
