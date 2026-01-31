cmake_minimum_required(VERSION 3.20)

project(hello-world CXX)

set(CMAKE_C_STANDARD 17)
set(CMAKE_CXX_STANDARD 20)

add_executable(myapp
    source/main.cpp
)

target_compile_definitions(myapp PRIVATE __3DS__)

target_link_libraries(myapp PRIVATE ctru)

# Export include dirs so IDE knows about them
target_include_directories(myapp SYSTEM PRIVATE $ENV{DEVKITPRO}/libctru/include)

# Post-build: convert ELF → 3DSX
add_custom_command(TARGET myapp POST_BUILD
        COMMAND ${DEVKITPRO}/tools/bin/3dsxtool
        $<TARGET_FILE:myapp>
        ${CMAKE_CURRENT_BINARY_DIR}/myapp.3dsx
)

# cmake -S . -B build \
#  -DCMAKE_TOOLCHAIN_FILE=$DEVKITPRO/cmake/3DS.cmake