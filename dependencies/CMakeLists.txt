set(BOOST_ROOT ${CMAKE_SOURCE_DIR}/../tools/boost/boost_1_72_0 PARENT_SCOPE)

add_subdirectory(catch2_proj)
add_subdirectory(cpputest_proj)
add_subdirectory(doctest_proj)
add_subdirectory(fmt_proj)
add_subdirectory(googletest_proj)
add_subdirectory(ut_proj)

