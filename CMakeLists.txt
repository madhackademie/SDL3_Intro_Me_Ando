cmake_minimum_required(VERSION 3.20)
project(ProtoSDL3Ando)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Recherche de SDL3
find_package(SDL3 REQUIRED)

# Exécutable
add_executable(${PROJECT_NAME} main.cpp)

# Liaison avec SDL3
target_link_libraries(${PROJECT_NAME} SDL3::SDL3)
