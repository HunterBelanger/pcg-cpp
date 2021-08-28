cmake_minimum_required(VERSION 3.11)

project(pcg-cpp_tests
  LANGUAGES CXX
)

add_executable(check-pcg8_once_insecure check-pcg8_once_insecure.cpp)
target_link_libraries(check-pcg8_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg8_oneseq_once_insecure check-pcg8_oneseq_once_insecure.cpp)
target_link_libraries(check-pcg8_oneseq_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg16_once_insecure check-pcg16_once_insecure.cpp)
target_link_libraries(check-pcg16_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg16_oneseq_once_insecure check-pcg16_oneseq_once_insecure.cpp)
target_link_libraries(check-pcg16_oneseq_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg32 check-pcg32.cpp)
target_link_libraries(check-pcg32 PUBLIC pcg-cpp)

add_executable(check-pcg32_c1024 check-pcg32_c1024.cpp)
target_link_libraries(check-pcg32_c1024 PUBLIC pcg-cpp)

add_executable(check-pcg32_c1024_fast check-pcg32_c1024_fast.cpp)
target_link_libraries(check-pcg32_c1024_fast PUBLIC pcg-cpp)

add_executable(check-pcg32_c64 check-pcg32_c64.cpp)
target_link_libraries(check-pcg32_c64 PUBLIC pcg-cpp)

add_executable(check-pcg32_c64_fast check-pcg32_c64_fast.cpp)
target_link_libraries(check-pcg32_c64_fast PUBLIC pcg-cpp)

add_executable(check-pcg32_c64_oneseq check-pcg32_c64_oneseq.cpp)
target_link_libraries(check-pcg32_c64_oneseq PUBLIC pcg-cpp)

add_executable(check-pcg32_fast check-pcg32_fast.cpp)
target_link_libraries(check-pcg32_fast PUBLIC pcg-cpp)

add_executable(check-pcg32_k1024 check-pcg32_k1024.cpp)
target_link_libraries(check-pcg32_k1024 PUBLIC pcg-cpp)

add_executable(check-pcg32_k1024_fast check-pcg32_k1024_fast.cpp)
target_link_libraries(check-pcg32_k1024_fast PUBLIC pcg-cpp)

add_executable(check-pcg32_k16384 check-pcg32_k16384.cpp)
target_link_libraries(check-pcg32_k16384 PUBLIC pcg-cpp)

add_executable(check-pcg32_k16384_fast check-pcg32_k16384_fast.cpp)
target_link_libraries(check-pcg32_k16384_fast PUBLIC pcg-cpp)

add_executable(check-pcg32_k2 check-pcg32_k2.cpp)
target_link_libraries(check-pcg32_k2 PUBLIC pcg-cpp)

add_executable(check-pcg32_k2_fast check-pcg32_k2_fast.cpp)
target_link_libraries(check-pcg32_k2_fast PUBLIC pcg-cpp)

add_executable(check-pcg32_k64 check-pcg32_k64.cpp)
target_link_libraries(check-pcg32_k64 PUBLIC pcg-cpp)

add_executable(check-pcg32_k64_fast check-pcg32_k64_fast.cpp)
target_link_libraries(check-pcg32_k64_fast PUBLIC pcg-cpp)

add_executable(check-pcg32_k64_oneseq check-pcg32_k64_oneseq.cpp)
target_link_libraries(check-pcg32_k64_oneseq PUBLIC pcg-cpp)

add_executable(check-pcg32_once_insecure check-pcg32_once_insecure.cpp)
target_link_libraries(check-pcg32_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg32_oneseq check-pcg32_oneseq.cpp)
target_link_libraries(check-pcg32_oneseq PUBLIC pcg-cpp)

add_executable(check-pcg32_oneseq_once_insecure check-pcg32_oneseq_once_insecure.cpp)
target_link_libraries(check-pcg32_oneseq_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg32_unique check-pcg32_unique.cpp)
target_link_libraries(check-pcg32_unique PUBLIC pcg-cpp)

add_executable(check-pcg64 check-pcg64.cpp)
target_link_libraries(check-pcg64 PUBLIC pcg-cpp)

add_executable(check-pcg64_c1024 check-pcg64_c1024.cpp)
target_link_libraries(check-pcg64_c1024 PUBLIC pcg-cpp)

add_executable(check-pcg64_c1024_fast check-pcg64_c1024_fast.cpp)
target_link_libraries(check-pcg64_c1024_fast PUBLIC pcg-cpp)

add_executable(check-pcg64_c32 check-pcg64_c32.cpp)
target_link_libraries(check-pcg64_c32 PUBLIC pcg-cpp)

add_executable(check-pcg64_c32_fast check-pcg64_c32_fast.cpp)
target_link_libraries(check-pcg64_c32_fast PUBLIC pcg-cpp)

add_executable(check-pcg64_c32_oneseq check-pcg64_c32_oneseq.cpp)
target_link_libraries(check-pcg64_c32_oneseq PUBLIC pcg-cpp)

add_executable(check-pcg64_fast check-pcg64_fast.cpp)
target_link_libraries(check-pcg64_fast PUBLIC pcg-cpp)

add_executable(check-pcg64_k1024 check-pcg64_k1024.cpp)
target_link_libraries(check-pcg64_k1024 PUBLIC pcg-cpp)

add_executable(check-pcg64_k1024_fast check-pcg64_k1024_fast.cpp)
target_link_libraries(check-pcg64_k1024_fast PUBLIC pcg-cpp)

add_executable(check-pcg64_k32 check-pcg64_k32.cpp)
target_link_libraries(check-pcg64_k32 PUBLIC pcg-cpp)

add_executable(check-pcg64_k32_fast check-pcg64_k32_fast.cpp)
target_link_libraries(check-pcg64_k32_fast PUBLIC pcg-cpp)

add_executable(check-pcg64_k32_oneseq check-pcg64_k32_oneseq.cpp)
target_link_libraries(check-pcg64_k32_oneseq PUBLIC pcg-cpp)

add_executable(check-pcg64_once_insecure check-pcg64_once_insecure.cpp)
target_link_libraries(check-pcg64_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg64_oneseq check-pcg64_oneseq.cpp)
target_link_libraries(check-pcg64_oneseq PUBLIC pcg-cpp)

add_executable(check-pcg64_oneseq_once_insecure check-pcg64_oneseq_once_insecure.cpp)
target_link_libraries(check-pcg64_oneseq_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg64_unique check-pcg64_unique.cpp)
target_link_libraries(check-pcg64_unique PUBLIC pcg-cpp)

add_executable(check-pcg128_once_insecure check-pcg128_once_insecure.cpp)
target_link_libraries(check-pcg128_once_insecure PUBLIC pcg-cpp)

add_executable(check-pcg128_oneseq_once_insecure check-pcg128_oneseq_once_insecure.cpp)
target_link_libraries(check-pcg128_oneseq_once_insecure PUBLIC pcg-cpp)

add_custom_target(copy-runtime-files ALL
  COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_CURRENT_SOURCE_DIR}/run-tests.sh ${CMAKE_CURRENT_BINARY_DIR}/run-tests.sh
  COMMAND ${CMAKE_COMMAND} -E copy_directory ${CMAKE_CURRENT_SOURCE_DIR}/expected ${CMAKE_CURRENT_BINARY_DIR}/expected
  DEPENDS ${MY_TARGET}
)

add_test(NAME run-tests.sh COMMAND run-tests.sh)
