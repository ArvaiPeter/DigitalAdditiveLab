# GLFW
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(glfw)

# ImGui
add_library(imgui STATIC)

target_sources(imgui
               PRIVATE imgui/imgui_draw.cpp
                       imgui/imgui_tables.cpp
                       imgui/imgui_widgets.cpp
                       imgui/imgui.cpp
                       imgui/imgui_demo.cpp
                       
                       imgui/backends/imgui_impl_glfw.cpp
                       imgui/backends/imgui_impl_opengl3.cpp)

target_include_directories(imgui PUBLIC imgui
                                        imgui/backends)

target_link_libraries(imgui PRIVATE glfw)
