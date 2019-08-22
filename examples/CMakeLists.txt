include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../include)

find_package(OpenSSL)

# c_example
add_executable(c_example ${CMAKE_CURRENT_SOURCE_DIR}/c_example.c)
target_link_libraries(c_example LINK_PUBLIC count ${OPENSSL_LIBRARIES})

# cc_example
add_executable(cc_example ${CMAKE_CURRENT_SOURCE_DIR}/cc_example.cc)
target_link_libraries(cc_example LINK_PUBLIC count ${OPENSSL_LIBRARIES})

# certify
add_executable(certify ${CMAKE_CURRENT_SOURCE_DIR}/certify.cc)
target_link_libraries(certify LINK_PUBLIC count ${OPENSSL_LIBRARIES})

# Run the 'certify' binary
add_custom_target(check-certify
        DEPENDS certify
        COMMAND ${CMAKE_BINARY_DIR}/examples/certify)

# merge_example
add_executable(merge_example ${CMAKE_CURRENT_SOURCE_DIR}/merge_example.cc)
target_link_libraries(merge_example LINK_PUBLIC count ${OPENSSL_LIBRARIES})
