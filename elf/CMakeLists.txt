
add_custom_command(
    OUTPUT to_string.cc
    COMMAND ${CMAKE_COMMAND} -P ${CMAKE_CURRENT_SOURCE_DIR}/generate_to_string.cmake)

add_library(elf++ common.hh data.hh elf.cc elf++.hh mmap_loader.cc to_hex.hh to_string.cc)
target_include_directories(elf++ PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

set_property(TARGET elf++ PROPERTY POSITION_INDEPENDENT_CODE ON)