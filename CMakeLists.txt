enable_testing()
add_subdirectory(third_party/googletest-release-1.10.0)
include_directories(third_party/googletest-release-1.10.0/googletest/include)
set(GTEST_LIB gtest gtest_main)

add_executable(test_add test/c/test_add.cc)
add_executable(test_minus test/c/test_minus.cc)
target_link_libraries(test_add math gtest gtest_main)
target_link_libraries(test_minus math gtest gtest_main)

add_test(NAME test_add COMMAND test_add)
add_test(NAME test_minus COMMAND test_minus)