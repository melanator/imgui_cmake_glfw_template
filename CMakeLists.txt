cmake_minimum_required(VERSION 3.15)

set(CMAKE_CXX_STANDARD 17)

project (cmake_imgui_template)

add_subdirectory(external/googletest)
add_subdirectory(external/glfw)
add_subdirectory(external/glew/build/cmake)
add_subdirectory(tests)

set (IMGUI_DIR external/imgui)
file(GLOB IMGUI_CPP ${IMGUI_DIR}/*.cpp)
add_library(imgui ${IMGUI_CPP})
target_link_libraries(imgui glfw)
target_include_directories(imgui PRIVATE external/glfw/include)


add_library(glad external/glad/src/glad.c)

add_executable (${PROJECT_NAME} "code/main.cpp")
target_include_directories (${PROJECT_NAME} PUBLIC 
											external/glfw/include 
											external/glad/include
											external/glew/include
											external/imgui
)

target_link_libraries (${PROJECT_NAME} glfw 
									   glad 
									   glew 
									   imgui
)