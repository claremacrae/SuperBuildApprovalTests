# -------------------------------------------------------------------
# ApprovalTests.cpp

# CMake in the parent directory will have already added all our dependencies.
# Here, by asking ApprovalTests.cpp to include its own third_party projects,
# we check that they check to avoid creating targets that already exist.
set(APPROVAL_TESTS_BUILD_THIRD_PARTY
        ON CACHE BOOL "" FORCE)

set(APPROVAL_TESTS_BUILD_TESTING
        ON CACHE BOOL "" FORCE)
set(APPROVAL_TESTS_BUILD_EXAMPLES
        ON CACHE BOOL "" FORCE)
set(APPROVAL_TESTS_BUILD_CMAKE_INTEGRATION_TESTING
        ON CACHE BOOL "" FORCE)

add_subdirectory(
        ${CMAKE_SOURCE_DIR}/../ApprovalTests/ApprovalTests.cpp
        ${CMAKE_CURRENT_BINARY_DIR}/build
)
