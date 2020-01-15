# -------------------------------------------------------------------
# GoogleTest
# Prevent GoogleTest from overriding our compiler/linker options
# when building with Visual Studio
set(gtest_force_shared_crt
        ON CACHE BOOL "" FORCE)
add_subdirectory(
        ../../Testing/googletest
        ${CMAKE_CURRENT_BINARY_DIR}/build
)
