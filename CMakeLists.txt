cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(photo C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CAKE_CXX_STANDARD 17)

pico_sdk_init()

add_executable(photo
	main.c
)

pico_enable_stdio_usb(photo 1)
pico_enable_stdio_uart(photo 1)

pico_add_extra_outputs(photo)

target_link_libraries(photo pico_stdlib hardware_adc)
