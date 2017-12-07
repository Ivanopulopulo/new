cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)

include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/Ivanopulopulo/hunter/archive/v0.19.137.1.tar.gz"
SHA1 "0ac862bc0cc66a0833faf8ce0433facfb833f9e5"
)

project(example)

hunter_add_package(stack)
find_package(stack)

add_executable(example ${CMAKE_CURRENT_SOURCE_DIR}/sources/example.cpp)
target_link_libraries(example stack)

install(TARGETS example RUNTIME DESTINATION bin)
