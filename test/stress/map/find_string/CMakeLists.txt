set(PACKAGE_NAME stress-map-find-string)

set(CDSSTRESS_MAP_FIND_STRING_SOURCES
    ../../main.cpp
    map_find_string.cpp
    map_find_string_bronsonavltree.cpp
    map_find_string_cuckoo.cpp
    map_find_string_ellentree.cpp
    map_find_string_feldman_hashset.cpp
    map_find_string_michael.cpp
    map_find_string_skip.cpp
    map_find_string_split.cpp
    map_find_string_std.cpp
    map_find_string_striped.cpp
)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/..
)

add_executable(${PACKAGE_NAME} ${CDSSTRESS_MAP_FIND_STRING_SOURCES})
target_link_libraries(${PACKAGE_NAME} ${CDS_TEST_LIBRARIES} ${CDSSTRESS_FRAMEWORK_LIBRARY})

add_test(NAME ${PACKAGE_NAME} COMMAND ${PACKAGE_NAME} WORKING_DIRECTORY ${EXECUTABLE_OUTPUT_PATH})