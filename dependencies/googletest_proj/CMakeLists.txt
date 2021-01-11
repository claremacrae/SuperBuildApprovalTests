# -------------------------------------------------------------------
# GoogleTest
# Prevent GoogleTest from overriding our compiler/linker options
# when building with Visual Studio
set(gtest_force_shared_crt
        ON CACHE BOOL "" FORCE)
add_subdirectory(
        ${CMAKE_SOURCE_DIR}/../Testing/googletest
        ${CMAKE_CURRENT_BINARY_DIR}/build
)
