# -------------------------------------------------------------------
# Catch2
set(CATCH_BUILD_TESTING
        OFF CACHE BOOL "" FORCE)
add_subdirectory(
        ../../cpp/Catch2
        ${CMAKE_CURRENT_BINARY_DIR}/build
)
