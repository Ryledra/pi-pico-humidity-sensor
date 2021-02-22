cmake_minimum_required(VERSION 3.12)

include(pico_sdk_init.cmake)


project(project1
        LANGUAGES ASM C CXX
        VERSION 0.1
        DESCRIPTION "humidity-sensors"
)


set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)


set(FILE_ELF ${CMAKE_PROJECT_NAME}.elf)
set(FILE_HEX ${CMAKE_PROJECT_NAME}.hex)


# Initialize the SDK
pico_sdk_init()


add_executable(main
    main.cpp
)

target_sources(main
    PUBLIC
        ${CMAKE_CURRENT_LIST_DIR}/../lib/sd1306/SSD1306.cpp
        ${CMAKE_CURRENT_LIST_DIR}/../lib/sd1306/GFX.cpp
)

target_include_directories(main
    PUBLIC
        ${CMAKE_CURRENT_LIST_DIR}/../
)


target_link_libraries(main
  pico_stdlib
  hardware_i2c
)

pico_add_extra_outputs(main)
