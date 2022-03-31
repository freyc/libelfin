add_custom_command(
    OUTPUT to_string.cc
    COMMAND ${CMAKE_COMMAND} -P ${CMAKE_CURRENT_SOURCE_DIR}/generate_to_string.cmake)

add_library(dwarf++ 
    abbrev.cc 
    attrs.cc 
    cursor.cc 
    data.hh 
    die_str_map.cc 
    die.cc 
    dwarf.cc 
    dwarf++.hh 
    elf.cc 
    expr.cc 
    internal.hh 
    line.cc 
    rangelist.cc 
    small_vector.hh 
    value.cc 
    to_string.cc)

target_include_directories(dwarf++ PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
set_property(TARGET dwarf++ PROPERTY POSITION_INDEPENDENT_CODE ON)