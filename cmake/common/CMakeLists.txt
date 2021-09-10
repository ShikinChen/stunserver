cmake_minimum_required(VERSION 3.20)
project("common")

set(COMMON_PATH ${STUNSERVER_PATH}/common)

file(GLOB COMMON_SRC_PATH
        ${COMMON_PATH}/*.cpp
        ${COMMON_PATH}/*.hpp
        )

add_library(
        common
        SHARED
        ${COMMON_SRC_PATH})

target_include_directories(common
        PUBLIC
        ${COMMON_PATH}
        )