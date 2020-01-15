# -------------------------------------------------------------------
# ApprovalTests.cpp

set(APPROVAL_TESTS_BUILD_THIRD_PARTY
        ON CACHE BOOL "" FORCE)
set(APPROVAL_TESTS_BUILD_TESTING
        ON CACHE BOOL "" FORCE)
set(APPROVAL_TESTS_BUILD_EXAMPLES
        ON CACHE BOOL "" FORCE)
set(APPROVAL_TESTS_BUILD_CMAKE_INTEGRATION_TESTING
        ON CACHE BOOL "" FORCE)

add_subdirectory(
        ../../ApprovalTests/ApprovalTests.cpp
        ${CMAKE_CURRENT_BINARY_DIR}/build
)
