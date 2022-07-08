#
# Build scripts to work with book examples
#
cmake_minimum_required(VERSION 3.20)

project(Hands-On-Design-Patterns-with-CPP 
    VERSION 1.0.0
    DESCRIPTION "Examples from Packt's Book Hands-On Design Patterns with C++"
    HOMEPAGE_URL "https://www.packtpub.com/product/hands-on-design-patterns-with-c/9781788832564"
    LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

if(EXISTS ${CMAKE_BINARY_DIR}/conan_paths.cmake)
    include(${CMAKE_BINARY_DIR}/conan_paths.cmake)
else()
    message(FATAL_ERROR "conan_paths.cmake not found! run 'conan install' first.")
endif()

find_package(GTest REQUIRED)
find_package(benchmark REQUIRED)

enable_testing()

set(SUBPROJECTS
    Chapter04 Chapter05 Chapter06 Chapter07 Chapter08 Chapter09 Chapter10 Chapter11
    Chapter12 Chapter13 Chapter15 Chapter16 Chapter17 Chapter18)

foreach(_subfolder ${SUBPROJECTS})
    add_subdirectory(${_subfolder})
endforeach()