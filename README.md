# SuperBuildApprovalTests

An way to build all ApprovalTests projects and their dependencies in one CLion project.

## Benefits

* Quickly test interactions between libraries
* Run all tests in one go:
    * `cmake . && cmake --build . && ctest . --output-on-failure
`
* Can easily switch between different versions of dependencies, e.g. to update Boost.UT to a particular version, and then run all our tests
* Could be used to `git bisect` to track down a problem in a project that affects another project
* Easier to debug through 3rd-party dependency code, as e.g. Catch2 won't be using its single header
* Can test bug-fixes for one library in another, without having to create a single-header release to test the result 
* Can create shelves that contain files from multiple projects
* Can (presumably) refactor across projects