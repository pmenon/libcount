include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../include)

add_executable(mkdata
        ${CMAKE_CURRENT_SOURCE_DIR}/raw_data.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/mkdata.cc)

target_link_libraries(mkdata LINK_PUBLIC)