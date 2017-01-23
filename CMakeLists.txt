cmake_minimum_required(VERSION 3.7.0)
project(cmake-implib)

include(ExternalProject)

add_subdirectory(lib)
add_library(implibtop STATIC IMPORTED)
add_dependencies(implibtop lib)
set_property(TARGET implibtop PROPERTY IMPORTED_LOCATION $<TARGET_FILE:lib>)

add_subdirectory(execlib)
add_subdirectory(execimplib)
add_subdirectory(execimplibtop)
