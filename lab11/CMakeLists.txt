cmake_minimum_required(VERSION 3.22)

project(
  CryptoLab
  VERSION 1.0
  DESCRIPTION "This is for lab12."
  LANGUAGES C)

add_executable(verifier lab11.c)

find_package(OpenSSL REQUIRED)
target_link_libraries(verifier OpenSSL::Crypto)
