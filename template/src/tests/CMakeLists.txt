
add_executable(helloworld helloworld.c)

# set include and lib path
include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)

# set bin path
set_target_properties(helloworld PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")

# Add the library we build project
find_package(PkgConfig REQUIRED)

# # Resolve Mac issue linking Openssl
set(ENV{PKG_CONFIG_PATH} "/usr/bin/pkg-config")

# pkg_check_modules(KAFKA REQUIRED IMPORTED_TARGET rdkafka)

# target_link_libraries(helloworld PRIVATE PkgConfig::KAFKA)
# # target_link_libraries(helloworld PRIVATE PkgConfig::KAFKA cjson)

add_library(hello SHARED helloworld.c)
set_target_properties(hello PROPERTIES LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib")