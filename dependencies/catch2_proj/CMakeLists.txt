# -------------------------------------------------------------------
# Catch2
set(CATCH_BUILD_TESTING
        OFF CACHE BOOL "" FORCE)
add_subdirectory(
        ${CMAKE_SOURCE_DIR}/../cpp/Catch2
        ${CMAKE_CURRENT_BINARY_DIR}/build
)
