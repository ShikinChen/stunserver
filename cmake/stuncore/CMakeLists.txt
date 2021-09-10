cmake_minimum_required(VERSION 3.20)
project("stuncore")

set(STUNCORE_PATH ${STUNSERVER_PATH}/stuncore)

file(GLOB STUNCORE_SRC_PATH
        ${STUNCORE_PATH}/*.cpp
        )

add_library(
        stuncore
        SHARED
        ${STUNCORE_SRC_PATH})


target_link_libraries(
        stuncore
        ${CONAN_LIBS} common)

target_include_directories(stuncore
        PUBLIC
        ${STUNCORE_PATH}
        )
