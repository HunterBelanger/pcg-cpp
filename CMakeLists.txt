cmake_minimum_required(VERSION 3.11)

project(pcg-cpp
  VERSION "0.2.1"
  DESCRIPTION "PCG random number generator."
  LANGUAGES CXX
)

include(CMakePackageConfigHelpers)

# Add options
option(PCG_CPP_TESTS "Build PCG tests" OFF)
option(PCG_CPP_EXAMPLES "Build PCG examples" OFF)
option(PCG_CPP_INSTALL "Install PCG-CPP" ON)

add_library(pcg-cpp INTERFACE)
# Add alias to make more friendly with FetchConent
add_library(PCG_CXX ALIAS pcg-cpp)
add_library(PCG::PCG_CXX ALIAS pcg-cpp)

# Add public interface includes directory
target_include_directories(pcg-cpp INTERFACE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
)

# Require C++11 standard
target_compile_features(pcg-cpp INTERFACE cxx_std_11)

# If building tests, add the test-high subdirectory
if(PCG_CPP_TESTS)
  enable_testing()
  add_subdirectory(test-high)
endif()

# If building examples, add the sample subdirectory
if(PCG_CPP_EXAMPLES)
  enable_testing()
  add_subdirectory(sample)
endif()

# Install PCG-CPP
if(PCG_CPP_INSTALL)
  include(GNUInstallDirs)

  configure_package_config_file(${CMAKE_CURRENT_SOURCE_DIR}/pcg-cppConfig.cmake.in
    "${CMAKE_CURRENT_BINARY_DIR}/pcg-cppConfig.cmake"
    INSTALL_DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/pcg-cpp
  )

  write_basic_package_version_file(
    "${CMAKE_CURRENT_BINARY_DIR}/pcg-cppConfigVersion.cmake"
    VERSION "${pcg-cpp_VERSION}"
    COMPATIBILITY SameMinorVersion
  )

  install(TARGETS pcg-cpp
          EXPORT pcg-cppTargets
          LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
          ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
          RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
          INCLUDES DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
  )

  install(FILES "${CMAKE_CURRENT_SOURCE_DIR}/include/pcg_random.hpp"
                "${CMAKE_CURRENT_SOURCE_DIR}/include/pcg_extras.hpp"
                "${CMAKE_CURRENT_SOURCE_DIR}/include/pcg_uint128.hpp"
          DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})

  install(EXPORT pcg-cppTargets
          FILE pcg-cppTargets.cmake
          NAMESPACE PCG::
          DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/pcg-cpp
  )

  install(FILES
          "${CMAKE_CURRENT_BINARY_DIR}/pcg-cppConfig.cmake"
          "${CMAKE_CURRENT_BINARY_DIR}/pcg-cppConfigVersion.cmake"
          DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/pcg-cpp
  )
endif()
