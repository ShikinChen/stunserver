cmake_minimum_required(VERSION 3.20)
project("networkutils")

set(NETWORKUTILS_PATH ${STUNSERVER_PATH}/networkutils)

file(GLOB NETWORKUTILS_SRC_PATH
        ${NETWORKUTILS_PATH}/*.cpp
        )

add_library(
        networkutils
        SHARED
        ${NETWORKUTILS_SRC_PATH})

target_link_libraries(
        networkutils
        ${CONAN_LIBS} common stuncore)

target_include_directories(networkutils
        PUBLIC
        ${NETWORKUTILS_PATH}
        )