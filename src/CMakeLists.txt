set(COMMON_LIB common)
add_library("${COMMON_LIB}" SHARED compute.c)
target_link_libraries("${COMMON_LIB}" m)
set_target_properties("${COMMON_LIB}" PROPERTIES LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib")

add_subdirectory(tests)