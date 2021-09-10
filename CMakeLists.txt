cmake_minimum_required(VERSION 3.20)
project(stunserver)

IF (APPLE)#macOS系统环境变量
    set(CMAKE_MACOSX_RPATH OFF)
ENDIF ()

set(CMAKE_CXX_STANDARD 11)

add_definitions("-DDEBUG")

if (EXISTS ${CMAKE_SOURCE_DIR}/conanbuildinfo.cmake)
    include(${CMAKE_SOURCE_DIR}/conanbuildinfo.cmake) #如果使用 conan install . 命令 使用当前 conanbuildinfo.cmake
else ()
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake) # 如果使用 clion的conan 插件
endif ()

conan_basic_setup()
set(CMAKE_PATH ${CMAKE_CURRENT_LIST_DIR}/cmake)
set(STUNSERVER_PATH ${CMAKE_CURRENT_LIST_DIR}/stunserver)

file(GLOB RESOURCES_FILES
        ${STUNSERVER_PATH}/resources/*.txtcode
        )


add_subdirectory(${CMAKE_PATH}/common)
add_subdirectory(${CMAKE_PATH}/networkutils)
add_subdirectory(${CMAKE_PATH}/stuncore)

add_subdirectory(${CMAKE_PATH}/server)
add_subdirectory(${CMAKE_PATH}/client)

