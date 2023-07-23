cmake_minimum_required(VERSION 3.15)

set(CMAKE_CXX_STANDARD 17)

project (electrical)

add_subdirectory(external/googletest)
add_subdirectory(external/glfw)
add_subdirectory(tests)

add_executable (${PROJECT_NAME} "code/main.cpp")
target_include_directories (${PROJECT_NAME} PUBLIC external/glfw/include external/glad/include)
target_link_libraries (${PROJECT_NAME} glfw)