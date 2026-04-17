cmake_minimum_required(VERSION 3.20)
project(SimpleNetLib VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# ─── Library ──────────────────────────────────────────────────────────────────
add_library(simplenet
    src/Server.cpp
    src/Client.cpp
    src/Packet.cpp
    src/Connection.cpp
)

target_include_directories(simplenet PUBLIC include)

# Link Winsock2 on Windows
if(WIN32)
    target_link_libraries(simplenet PUBLIC ws2_32)
    target_compile_definitions(simplenet PUBLIC _WIN32_WINNT=0x0601)
endif()

# ─── Tests ────────────────────────────────────────────────────────────────────
enable_testing()
add_subdirectory(tests)

# ─── Examples ─────────────────────────────────────────────────────────────────
add_subdirectory(examples/chat)
