cmake_minimum_required (VERSION 3.5.0)
project (mcp3424)

FILE (GLOB SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/*.c")
FILE (GLOB HEADERS "${CMAKE_CURRENT_SOURCE_DIR}/*.h")

include_directories (BEFORE "${CMAKE_CURRENT_SOURCE_DIR}/")

SET (CMAKE_INCLUDE_CURRENT_DIR ON)

add_library (${PROJECT_NAME} SHARED ${SOURCES} ${HEADERS})

set_target_properties (${PROJECT_NAME} PROPERTIES VERSION 1.0 SOVERSION 1)

install (TARGETS ${PROJECT_NAME} DESTINATION /lib)
install (FILES ${HEADERS} DESTINATION /include)
