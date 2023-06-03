add_library(${MCU_MODEL} system_stm32l4xx.c)

target_include_directories(${MCU_MODEL} PRIVATE
        ${CMAKE_SOURCE_DIR}/core/${MCU_MODEL}/include
        ${CMAKE_SOURCE_DIR}/core/arm_cmsis/
        )