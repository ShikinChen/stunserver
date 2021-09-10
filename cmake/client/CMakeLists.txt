cmake_minimum_required(VERSION 3.20)
project("client")

set(CLIENT_PATH ${STUNSERVER_PATH}/client)

file(GLOB CLIENT_SRC_PATH
        ${CLIENT_PATH}/*.cpp
        )

file(COPY ${RESOURCES_FILES}
        DESTINATION ${CLIENT_PATH})

add_executable("client" ${CLIENT_SRC_PATH})

target_link_libraries(
        client
        common networkutils stuncore )
