set(TEST_BIN helloworld)
add_executable("${TEST_BIN}" helloworld.c)

# Add the library we build project
# find_package(PkgConfig REQUIRED)

# # Resolve Mac issue linking Openssl
# set(ENV{PKG_CONFIG_PATH} "/usr/bin/pkg-config")

# pkg_check_modules(KAFKA REQUIRED IMPORTED_TARGET rdkafka)

# target_link_libraries(helloworld PRIVATE PkgConfig::KAFKA)

# set bin path
set_target_properties("${TEST_BIN}" PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")
target_link_libraries("${TEST_BIN}" "${COMMON_LIB}")
