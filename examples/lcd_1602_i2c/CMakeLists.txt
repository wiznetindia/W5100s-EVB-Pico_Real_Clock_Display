

# # pull in common dependencies and additional i2c hardware support
# #target_link_libraries(lcd_1602_i2c pico_stdlib hardware_i2c)

# set(TARGET_NAME lcd_1602_i2c)

# add_executable(${TARGET_NAME}
#         ${TARGET_NAME}.c
#         )

# target_link_libraries(${TARGET_NAME} PRIVATE
#         pico_stdlib
#         hardware_spi
#         hardware_dma
#         lcd_1602_i2c 
#         pico_stdlib 
#         hardware_i2c
#         ETHERNET_FILES
#         SPI_FILES
#         DHCP_FILES
#         DNS_FILES
#         TIMER_FILES
#         LOOPBACK_FILES
#         )

# pico_enable_stdio_usb(${TARGET_NAME} 1)
# pico_enable_stdio_uart(${TARGET_NAME} 0)

# pico_add_extra_outputs(${TARGET_NAME})

# # create map/bin/hex file etc.
# #pico_add_extra_outputs(lcd_1602_i2c)

# # add url via pico_set_program_url
# #example_auto_set_url(lcd_1602_i2c)


add_executable(lcd_1602_i2c
        lcd_1602_i2c.c
        )

# pull in common dependencies and additional i2c hardware support
target_link_libraries(lcd_1602_i2c pico_stdlib hardware_i2c hardware_spi
         hardware_dma ETHERNET_FILES
                  SPI_FILES
                  SNTP_FILES
                  TIMER_FILES
                  TIMER_FILES
                  LOOPBACK_FILES)

# create map/bin/hex file etc.

pico_enable_stdio_usb(lcd_1602_i2c 1)
pico_enable_stdio_uart(lcd_1602_i2c 0)
pico_add_extra_outputs(lcd_1602_i2c)

# pico_add_extra_outputs(${TARGET_NAME})
# add url via pico_set_program_url
#example_auto_set_url(lcd_1602_i2c)