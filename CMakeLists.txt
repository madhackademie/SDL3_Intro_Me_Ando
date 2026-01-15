cmake_minimum_required(VERSION 3.20)
project(ProtoSDL3Ando)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Téléchargement et compilation automatique de SDL3
include(FetchContent)

FetchContent_Declare(
    SDL3
    GIT_REPOSITORY https://github.com/libsdl-org/SDL.git
    GIT_TAG        main  # Utilise la branche main (dernière version)
)

# Options de compilation pour SDL3
set(SDL_SHARED ON CACHE BOOL "" FORCE)
set(SDL_STATIC OFF CACHE BOOL "" FORCE)
set(SDL_TEST OFF CACHE BOOL "" FORCE)

# Télécharge et compile SDL3
FetchContent_MakeAvailable(SDL3)

# Exécutable
add_executable(${PROJECT_NAME} main.cpp)

# Liaison avec SDL3
target_link_libraries(${PROJECT_NAME} SDL3::SDL3)
