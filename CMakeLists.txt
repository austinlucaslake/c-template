cmake_minimum_required(VERSION 3.23.5 FATAL_ERROR)

cmake_policy(SET CMP0063 NEW)
cmake_policy(SET CMP0091 NEW)
project(
	c-template
	VERSION 0.1.0
	LANGUAGES C CXX
	DESCRIPTION "Template repository for C/C++ projects.")

set(CMAKE_C_STANDARD 17)
set(CMAKE_C_STANDARD_REQUIRED TRUE)
set(CMAKE_C_EXTENSIONS OFF)
set(CMAKE_C_VISIBILITY_PRESET hidden)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_VISIBILITY_PRESET hidden)

set(CMAKE_EXPORT_COMPILE_COMMANDS TRUE)
set(CMAKE_SKIP_BUILD_RPATH FALSE)
set(CMAKE_BUILD_WITH_INSTALL_RPATH FALSE)
set(CMAKE_INSTALL_RPATH_USE_LINK_PATH TRUE)
set(CMAKE_VISIBILITY_INLINES_HIDDEN 1)
set(CMAKE_INSTALL_PREFIX ${CMAKE_BINARY_DIR}/install)
set(CMAKE_MODULE_PATH ${CMAKE_BINARY_DIR} ${CMAKE_MODULE_PATH})
set(CMAKE_PREFIX_PATH ${CMAKE_BINARY_DIR} ${CMAKE_PREFIX_PATH})

option(BUILD_TESTING "Build tests" FALSE)
option(BUILD_SHARED_LIBS "Build shared libraries" FALSE)
option(BUILD_WITH_MT "Build libraries as MultiThreaded DLL (Windows Only)" FALSE)

include(CTest)
include(GNUInstallDirs)
include(CMakePackageConfigHelpers)
include(InstallRequiredSystemLibraries)
include(GenerateExportHeader)

add_subdirectory(src)
