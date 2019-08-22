include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../include)

add_library(count
        ${CMAKE_CURRENT_SOURCE_DIR}/c.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/empirical_data.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/hll.cc
        ${CMAKE_CURRENT_SOURCE_DIR}/hll_data.cc)

set_target_properties(count PROPERTIES OUTPUT_NAME "count")
target_include_directories(count PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})