cmake_minimum_required(VERSION 3.1)
project(test_package)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(vk-bootstrap REQUIRED CONFIG)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} vk-bootstrap::vk-bootstrap)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 14)
