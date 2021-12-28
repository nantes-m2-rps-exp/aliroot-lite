cmake_minimum_required(VERSION 3.16 FATAL_ERROR)

project(aliroot-lite LANGUAGES CXX)

include(CTest)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

include(GNUInstallDirs)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/stage/lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/stage/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/stage/bin)

set(BUILD_SHARED_LIBS ON)

find_package(ROOT REQUIRED COMPONENTS Tree Physics Matrix Minuit Geom Graf3d XMLParser)

add_subdirectory(steer)
add_subdirectory(base)
add_subdirectory(aod)
add_subdirectory(esd)
add_subdirectory(cdb)
add_subdirectory(ana-base)
add_subdirectory(ana-alice)
add_subdirectory(stat)
