cmake_minimum_required(VERSION 3.16)

project(DSADrivenOSSimulator
    VERSION 1.0.0
    DESCRIPTION "A DSA-driven operating system simulator"
    LANGUAGES CXX
)

# Use C++17 for every target in this project.
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Main simulator executable.
add_executable(os_simulator
    cli/main.cpp
)

# Make shared project headers available to the executable.
target_include_directories(os_simulator PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/common
)

# Enable useful compiler warnings.
if(MSVC)
    target_compile_options(os_simulator PRIVATE /W4)
else()
    target_compile_options(os_simulator PRIVATE -Wall -Wextra -Wpedantic)
endif()