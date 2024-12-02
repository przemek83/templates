# Table of contents
- [Overview](#overview)
- [CMake](#cmake)
- [.gitignore](#gitignore)
- [.clang-format](#clang-format)
- [Licensing](#licensing)

# Overview
This repository contains reusable files including:
- `CMake` files for base and test subproject.
- `.gitignore` file,
- `.clang-format` file.

# CMake
CMake templates for use in C++ projects and libraries. Expected structure of C++ project is one containing sources in the `src` directory and tests in `test` directory. Expected structure for C++ library is one containing sources in `src` directory, tests in `test` directory, public headers in `include/<library name>` and use examples in `examples`. Also, present are files supporting use of `GTest` and `Catch2` testing frameworks.

For standard C++ projects, use:
- `CMakeLists.txt` as the main project file,
- `Tests.cmake.catch2` or `Tests.cmake.gtest` for initializing the appropriate testing framework,
- `test/CMakeLists.txt.catch2` or `test/CMakeLists.txt.gtest` for testing subproject.

For C++ library projects, use:
- `CMakeLists.txt.library` as the main project file,
- `library_name.pc.in` for additional configuration needed by projects using library,
- `Tests.cmake.catch2` or `Tests.cmake.gtest` for initializing the appropriate testing framework,
- `test/CMakeLists.txt.catch2` or `test/CMakeLists.txt.gtest` for testing subproject.

Check out my other projects like `data-explorer`, `penna-model` or `cpputils` for usage examples.

# .gitignore
Adjusted version of stock GitHub one for C++ projects. Added some entries related to Python and VSC use.

# .clang-format
Format file for `clang-format` tool. To be used with C++ projects enforcing coherent formatting along codebase. Just copy it to your project and setup IDE to use it.

# Licensing
Software is released under the MIT license.
