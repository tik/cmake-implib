add_library(lib STATIC lib.cpp)

add_library(implib STATIC IMPORTED)
add_dependencies(implib lib)
set_property(TARGET implib PROPERTY IMPORTED_LOCATION $<TARGET_FILE:tgt1>)
