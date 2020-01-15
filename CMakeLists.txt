cmake_minimum_required(VERSION 3.15)
project(SuperBuildApprovalTests LANGUAGES CXX)

# Hack to prevent CTest-added targets from cluttering up CLion's list of targets
# See https://stackoverflow.com/questions/44949354/hide-automatically-generated-ctest-targets
set_property(GLOBAL PROPERTY CTEST_TARGETS_ADDED 1)
enable_testing()

# -------------------------------------------------------------------
# Catch2
set(CATCH_BUILD_TESTING false)
add_subdirectory(
        ../cpp/Catch2
        ${CMAKE_CURRENT_BINARY_DIR}/catch2
)

# -------------------------------------------------------------------
# doctest
add_subdirectory(
        ../Testing/doctest
        ${CMAKE_CURRENT_BINARY_DIR}/doctest
)

# -------------------------------------------------------------------
# GoogleTest
# Prevent GoogleTest from overriding our compiler/linker options
# when building with Visual Studio
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
add_subdirectory(
        ../Testing/googletest
        ${CMAKE_CURRENT_BINARY_DIR}/googletest
)

# -------------------------------------------------------------------
# Boost.ut
# ec49196855078d98738f54023b488b2f85299826 is the first commit that works with FetchContent
# TODO Add a Boost.UT issue asking for option names to have a prefix added
set(BUILD_BENCHMARKS OFF)
set(BUILD_EXAMPLES OFF)
set(BUILD_TESTS OFF)

add_subdirectory(
        ../Testing/ut
        ${CMAKE_CURRENT_BINARY_DIR}/ut
)

if ("${CMAKE_CXX_COMPILER_ID}" MATCHES "Clang")
    # Turn off some checks for issues that should be fixed in ApprovalTests code
    target_compile_options(boost.ut INTERFACE
            -Wno-newline-eof
            -Wno-shadow-field-in-constructor
            -Wno-weak-vtables
            -Wno-c99-extensions # Needed for Boost.ut, at least in v1.1.6
            )
endif()

# -------------------------------------------------------------------
# ApprovalTests.cpp

set(APPROVAL_TESTS_BUILD_ALL_CONTENTS true)
set(APPROVAL_TESTS_BUILD_ADD_TESTS true)
add_subdirectory(
        ../ApprovalTests/ApprovalTests.cpp
        ${CMAKE_CURRENT_BINARY_DIR}/approval_tests_cpp
)
