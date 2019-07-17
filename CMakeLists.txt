cmake_minimum_required(VERSION 3.5)
project(curltest)

#find_package(CURL REQUIRED)
#include_directories("/usr/lib/curl")
set(CURL_INCLUDE_DIR "/usr/include/curl/"  "${CMAKE_CURRENT_SOURCE_DIR}/include")
MESSAGE(STATUS "${CURL_INCLUDE_DIR}")
include_directories(${CURL_INCLUDE_DIR})

file(GLOB SOURCES_FILES ${CMAKE_CURRENT_SOURCE_DIR}/* ${CMAKE_CURRENT_SOURCE_DIR}/include/*)
add_executable(curltest ${SOURCES_FILES})

#target_link_libraries(curltest ${CUEL_LIBRARY})
target_link_libraries(curltest libcurl.so)
