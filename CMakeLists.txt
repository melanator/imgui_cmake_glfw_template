cmake_minimum_required(VERSION 3.15)

set(CMAKE_CXX_STANDARD 17)

project (electrical)

add_subdirectory(external/googletest)
add_subdirectory(tests)

add_executable (${PROJECT_NAME} "code/main.cpp")