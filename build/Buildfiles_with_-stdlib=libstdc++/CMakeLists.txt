cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
project(libtorch_cross_test)
list(APPEND CMAKE_PREFIX_PATH "/home/marcel/Documents/libs/libtorch")
find_package(Torch REQUIRED)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++14 -stdlib=libstdc++ ${TORCH_CXX_FLAGS}")

add_executable(example-app main.cpp)
target_link_libraries(example-app "${TORCH_LIBRARIES}")
set_property(TARGET example-app PROPERTY CXX_STANDARD 14)
