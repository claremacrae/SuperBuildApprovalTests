# -------------------------------------------------------------------
# CppUTest

# Prevent CppUTest's own tests from being built
set(TESTS OFF CACHE BOOL "")

# Prevent build of CppUTest from generating thousands of lines of
# -Wc++98-compat and -Wc++98-compat-pedantic warnings:
set(C++11 ON CACHE BOOL "Compile with C++11 support")

add_subdirectory(
        ${CMAKE_SOURCE_DIR}/../Testing/cpputest
        ${CMAKE_CURRENT_BINARY_DIR}/cpputest_build
)
