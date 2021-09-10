cmake_minimum_required(VERSION 3.20)
project("server")

set(SERVER_PATH ${STUNSERVER_PATH}/server)

file(GLOB SERVER_SRC_PATH
        ${SERVER_PATH}/*.cpp
        )

add_executable("server" ${SERVER_SRC_PATH})

file(COPY ${RESOURCES_FILES}
        DESTINATION ${SERVER_PATH})


target_link_libraries(
        server
        common networkutils stuncore )
