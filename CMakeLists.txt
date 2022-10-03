# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(PROJECT "amiga_mouse")

# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "${CMAKE_CURRENT_LIST_DIR}/../pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(amiga_mouse C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(amiga_mouse src/main.c )

pico_set_program_name(amiga_mouse ${PROJECT})
pico_set_program_version(amiga_mouse "0.1")

pico_enable_stdio_uart(amiga_mouse 1)
pico_enable_stdio_usb(amiga_mouse 0)

target_include_directories(amiga_mouse BEFORE PUBLIC ${CMAKE_CURRENT_LIST_DIR} include)

# Add the standard library to the build
target_link_libraries(amiga_mouse PUBLIC pico_stdlib tinyusb_host tinyusb_board)

pico_add_extra_outputs(amiga_mouse)

