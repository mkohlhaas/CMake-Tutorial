cmake_minimum_required(VERSION 3.28.0)

project(Tutorial
        VERSION 1.0)


message("bindir: ${CMAKE_BINARY_DIR}")

set(CXX_STANDARD_REQUIRED On)
set(CXX_STANDARD 11)

configure_file(TutorialConfig.h.in TutorialConfig.h)

add_executable(Tutorial tutorial.cxx)

target_include_directories(Tutorial PUBLIC ${CMAKE_BINARY_DIR})
