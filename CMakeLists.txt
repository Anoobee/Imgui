cmake_minimum_required(VERSION 3.12)
project(ImGuiExample)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add the source files
set(SOURCES
    src/main.cpp
)

# Add ImGui source files
set(IMGUI_DIR lib)

# ImGui dependencies
set(IMGUI_SOURCES
    ${IMGUI_DIR}/imgui.cpp
    ${IMGUI_DIR}/imgui_impl_glfw.cpp
    ${IMGUI_DIR}/imgui_impl_opengl3.cpp
)

# Include directories
include_directories(${IMGUI_DIR})

# Add executable
add_executable(ImGuiExample ${SOURCES} ${IMGUI_SOURCES})

# Link against the necessary libraries
target_link_libraries(ImGuiExample PRIVATE ${CMAKE_SOURCE_DIR}/lib/glfw3.lib opengl32.lib)

# Set additional compiler flags if needed
# target_compile_options(ImGuiExample PRIVATE ...)

