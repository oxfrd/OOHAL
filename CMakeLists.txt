cmake_minimum_required(VERSION 3.14)

#########################################
#   APP SPECIFIC
#########################################
project(OOHAL VERSION 1.0)
set(MCU_MODEL STM32L476)
set(CMAKE_TOOLCHAIN_FILE Toolchain-arm-gcc.cmake)

message(STATUS "")
message(STATUS "##############################")
message(STATUS "### PROJECT:    " ${PROJECT_NAME})
message(STATUS "### MCU MODEL:  " ${MCU_MODEL})
message(STATUS "### VERSION:    " ${PROJECT_VERSION})
message(STATUS "##############################")
message(STATUS "")

add_subdirectory(core/${MCU_MODEL})

add_executable(${PROJECT_NAME} main.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE
        ${CMAKE_SOURCE_DIR}/core/${MCU_MODEL}/include
        ${CMAKE_SOURCE_DIR}/core/arm_cmsis/
        )
target_link_libraries(${PROJECT_NAME} PRIVATE ${MCU_MODEL})
