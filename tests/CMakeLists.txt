cmake_minimum_required (VERSION 3.15)

set(This tests)

add_executable(tests "./tests.cpp")

add_test(
	NAME ${This}
	COMMAND ${This})

target_link_libraries(tests PUBLIC gtest)

include(GoogleTest)
gtest_discover_tests(tests)

