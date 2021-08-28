cmake_minimum_required(VERSION 3.11)

project(pcg-cpp_samples
  LANGUAGES CXX
)

add_executable(codebook codebook.cpp)
target_link_libraries(codebook PUBLIC PCG_CXX)

add_executable(cppref-sample cppref-sample.cpp)
target_link_libraries(cppref-sample PUBLIC PCG_CXX)

add_executable(make-partytrick make-partytrick.cpp)
target_link_libraries(make-partytrick PUBLIC PCG_CXX)

add_executable(use-partytrick use-partytrick.cpp)
target_link_libraries(use-partytrick PUBLIC PCG_CXX)

add_executable(pcg-demo pcg-demo.cpp)
target_link_libraries(pcg-demo PUBLIC PCG_CXX)
