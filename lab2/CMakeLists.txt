cmake_minimum_required(VERSION 3.22)
project(lab2)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_C_STANDARD 17)

include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/refs/tags/v1.14.0.zip
)

set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable(
  lab2
  test_RB_tree.cpp
  RB_tree.c
  insertRBTree.c
  RB_tree_Rotate.c
  deleteRBTree.c
  RB_tree.h
)
target_link_libraries(
  lab2
  GTest::gtest_main
)

include(GoogleTest)
gtest_discover_tests(lab2)

