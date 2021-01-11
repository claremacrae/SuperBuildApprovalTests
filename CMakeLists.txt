cmake_minimum_required(VERSION 3.15)
project(SuperBuildApprovalTests LANGUAGES CXX)

# Hack to prevent CTest-added targets from cluttering up CLion's list of targets
# See https://stackoverflow.com/questions/44949354/hide-automatically-generated-ctest-targets
set_property(GLOBAL PROPERTY CTEST_TARGETS_ADDED 1)
enable_testing()

# TODO Add variables to control each of the sub-directories
# TODO Only add the source-dirs of they exist
# TODO Add a variable to control the location of the dependencies

add_subdirectory(dependencies)

add_subdirectory(approval_tests_cpp_proj)
add_subdirectory(approval_tests_cpp_starter_project_proj)

add_subdirectory(approval_tests_cpp_qt_proj)
add_subdirectory(approval_tests_cpp_qt_starter_project_proj)

add_subdirectory(approval_tests_cpp_cmake_samples_proj)
add_subdirectory(approval_tests_cpp_demos_proj)
add_subdirectory(approval_tests_cpp_nursery_proj)
