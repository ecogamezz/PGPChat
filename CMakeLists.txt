cmake_minimum_required(VERSION 3.15)
project(MyPGPChat LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Wenn du vcpkg als Submodul benutzt, kannst du (optional) diese Zeile verwenden:
# set(CMAKE_TOOLCHAIN_FILE "${CMAKE_CURRENT_SOURCE_DIR}/vcpkg/scripts/buildsystems/vcpkg.cmake"
#     CACHE FILEPATH "Vcpkg toolchain file")

# Optional: Falls du vcpkg im Manifest-Mode (vcpkg.json) verwendest, reicht das dem CMake bei passenden Parametern.

# ImGui + deine Dateien
set(SOURCES
    src/main.cpp
    src/ChatServer.cpp
    src/ChatServer.h
    src/ChatClient.cpp
    src/ChatClient.h
    src/CryptoGPGME.cpp
    src/CryptoGPGME.h
    # ImGui-Files:
    imgui/imgui.cpp
    imgui/imgui_draw.cpp
    imgui/imgui_widgets.cpp
    imgui/imgui_tables.cpp
    imgui/backends/imgui_impl_glfw.cpp
    imgui/backends/imgui_impl_opengl3.cpp
)

add_executable(MyPGPChat ${SOURCES})

# Nun "find_package" oder target_link_libraries: 
# find_package(GPGME REQUIRED)
# find_package(glfw3 CONFIG REQUIRED)
# find_package(OpenGL REQUIRED)
# etc.

# Dann z.B.
# target_link_libraries(MyPGPChat GPGME::GPGME glfw ${OPENGL_LIBRARIES} ...)
