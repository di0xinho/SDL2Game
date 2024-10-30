cmake_minimum_required(VERSION 3.7)

project(SDL2Game)

# Ustaw bezpośrednie ścieżki do plików SDL2
set(SDL2_INCLUDE_DIR "$ENV{VCPKG_ROOT}/packages/sdl2_x64-windows/include")
set(SDL2_LIB_DIR "$ENV{VCPKG_ROOT}/packages/sdl2_x64-windows/lib")

# Dodaj pliki źródłowe
file(GLOB SOURCES "src/*.cpp")

# Tworzenie pliku wykonywalnego
add_executable(SDL2Game ${SOURCES})

# Uwzględnij pliki nagłówkowe i biblioteki SDL2
include_directories(${SDL2_INCLUDE_DIR})
target_link_libraries(SDL2Game ${SDL2_LIB_DIR}/SDL2.lib ${SDL2_LIB_DIR}/manual-link/SDL2main.lib)