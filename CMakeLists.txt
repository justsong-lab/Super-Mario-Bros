cmake_minimum_required(VERSION 3.16)
project(mario CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

find_package(SFML 2.5 REQUIRED COMPONENTS graphics window)

FILE(GLOB Sources Source/*.cpp)
add_executable(mario
    ${Sources}
)
target_include_directories(mario PRIVATE Source/Headers)
target_link_libraries(mario PRIVATE sfml-graphics sfml-window)
install(TARGETS mario)
