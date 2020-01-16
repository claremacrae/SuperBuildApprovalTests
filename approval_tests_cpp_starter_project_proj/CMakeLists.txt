# -------------------------------------------------------------------
# ApprovalTests.cpp.StarterProject

# TODO Note that this only pulls in its own copy of the last ApprovalTests release.
# See https://github.com/approvals/ApprovalTests.cpp.StarterProject/issues/9 for what is needed
# to fix this.

add_subdirectory(
        ../../ApprovalTests/ApprovalTests.cpp.StarterProject
        ${CMAKE_CURRENT_BINARY_DIR}/build
)
