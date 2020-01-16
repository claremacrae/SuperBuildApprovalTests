# SuperBuildApprovalTests

A way to build all ApprovalTests projects and their dependencies in one CLion project.

## Benefits

* **Developing**
    * Quickly test interactions between libraries
    * No context-switching between different IDE instances
    * Can easily switch between different versions of dependencies, e.g. to update Boost.UT to a particular version, and then run all our tests. This might be useful before updating our own copies of 3rd-party libraries
    * Can (presumably) refactor across projects
* **Running Tests**
    * Run all tests in one go:
        * `cmake . && cmake --build . && ctest . --output-on-failure
    `
* **Bug-fixing**
    * Easier to debug through 3rd-party dependency code, as e.g. Catch2 won't be using its single header
    * Can test bug-fixes for one library in another, without having to create a single-header release to test the result 
* **Version Control**
    * Can see history in date-order across multiple projects (in CLion)
    * Can create shelves that contain files from multiple projects
    * Could be used to `git bisect` to track down a problem in a project that affects another project
* **Releases**
    * Eventually, test all projects with a new release, by adding the ability to select to load the single header, rather than the ApprovalTests.cpp source-code directory

## Alternatives

* FetchContent - which traditionally puts the cloned repo in the build space, which means you get one per build config, and finding the source code is a pain

## TODOs

* Make the starter project pick up header from main project, if present. Test by renaming CombinationApprovals to CombinationApprovalsXX
* Try this on Windows in Visual Studio and CLion
* Try refactoring across projects
* Add the Qt projects
* Add the Nursery project
* Try improving target names
