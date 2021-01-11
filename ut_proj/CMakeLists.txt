# -------------------------------------------------------------------
# Boost.ut
# ec49196855078d98738f54023b488b2f85299826 is the first commit that works with FetchContent
# TODO Add a Boost.UT issue asking for option names to have a prefix added
set(BUILD_BENCHMARKS
        OFF CACHE BOOL "" FORCE)
set(BUILD_EXAMPLES
        OFF CACHE BOOL "" FORCE)
set(BUILD_TESTS
        OFF CACHE BOOL "" FORCE)

add_subdirectory(
        ${CMAKE_SOURCE_DIR}/../Testing/ut
        ${CMAKE_CURRENT_BINARY_DIR}/build
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
