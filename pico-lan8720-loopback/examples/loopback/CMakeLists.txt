cmake_minimum_required(VERSION 3.12)

# rest of your project
add_executable(pico_rmii_ethernet_loopback
    main.c
)

target_link_libraries(pico_rmii_ethernet_loopback pico_stdlib pico_multicore pico_rmii_ethernet)

# enable usb output, disable uart output
pico_enable_stdio_usb(pico_rmii_ethernet_loopback 1)
pico_enable_stdio_uart(pico_rmii_ethernet_loopback 0)

# create map/bin/hex/uf2 file in addition to ELF.
pico_add_extra_outputs(pico_rmii_ethernet_loopback)
