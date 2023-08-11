cmake_minimum_required(VERSION 3.25)
project(cpp2lexer)

set(CMAKE_CXX_STANDARD 23)

add_custom_command(
    OUTPUT  main.cpp
    COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/../cppfront/cmake-build-release/cppfront
        -p
        -o ${CMAKE_CURRENT_BINARY_DIR}/main.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp2
    DEPENDS main.cpp2
)

add_executable(cpp2lexer ${CMAKE_CURRENT_BINARY_DIR}/main.cpp)
target_include_directories(cpp2lexer PRIVATE ./../cppfront/include)
