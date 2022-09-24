# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "/home/pi/repos/pico/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(amiga_keyboard C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(amiga_keyboard amiga_keyboard.c )

pico_set_program_name(amiga_keyboard "amiga_keyboard")
pico_set_program_version(amiga_keyboard "0.1")

pico_enable_stdio_uart(amiga_keyboard 1)
pico_enable_stdio_usb(amiga_keyboard 0)

target_include_directories(amiga_keyboard PRIVATE ${CMAKE_CURRENT_LIST_DIR})

# Add the standard library to the build
target_link_libraries(amiga_keyboard PRIVATE pico_stdlib tinyusb_host tinyusb_board)

pico_add_extra_outputs(amiga_keyboard)

