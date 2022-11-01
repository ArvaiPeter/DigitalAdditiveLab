cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(DigitalAdditiveLab VERSION 0.1)

add_subdirectory(lib)

find_package(OpenGL REQUIRED)

file(GLOB SRCFILES src/*.cpp)
add_executable(${PROJECT_NAME} ${SRCFILES})

target_link_libraries(${PROJECT_NAME} PRIVATE glfw
                                              imgui
                                              OpenGL::GL)



