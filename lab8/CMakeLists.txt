cmake_minimum_required(VERSION 3.22)

project(
  Lab8
  VERSION 1.0
  DESCRIPTION "This is an example for the lab."
  LANGUAGES C)

set(CMAKE_BUILD_TYPE Debug)

# Note: ASan and TSan are incompatible
# Address sanitization:
# add_compile_options(-fsanitize=address) 
# add_link_options(-fsanitize=address)
# --------- Task 3 ---------
# Enable the thread sanitizer 
# TODO


add_compile_options(-pthread)
add_link_options(-pthread)

add_executable(main src/lab8.c)
target_include_directories(main PRIVATE include)

