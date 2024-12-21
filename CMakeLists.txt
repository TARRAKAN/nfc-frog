cmake_minimum_required(VERSION 3.6)
project(nfc-frog)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -W -Wall -pedantic")

find_package(PkgConfig REQUIRED)
pkg_check_modules(LIBNFC REQUIRED libnfc)
include_directories(${LIBNFC_INCLUDE_DIRS})

set(SRC 
    main.cpp
    device_nfc.cpp
)

include_directories("headers/")

add_executable(${PROJECT_NAME} ${SRC})

target_link_libraries(${PROJECT_NAME} ${LIBNFC_LIBRARIES})