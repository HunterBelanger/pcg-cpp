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

add_library(PCG_CXX INTERFACE)
# Add alias to make more friendly with FetchConent
add_library(PCG::PCG_CXX ALIAS PCG_CXX)

# Add public interface includes directory
target_include_directories(PCG_CXX INTERFACE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
)

# Require C++11 standard
target_compile_features(PCG_CXX INTERFACE cxx_std_11)

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

  configure_package_config_file(${CMAKE_CURRENT_SOURCE_DIR}/PCG_CXXConfig.cmake.in
    "${CMAKE_CURRENT_BINARY_DIR}/PCG_CXXConfig.cmake"
    INSTALL_DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/PCG_CXX
  )

  write_basic_package_version_file(
    "${CMAKE_CURRENT_BINARY_DIR}/PCG_CXXConfigVersion.cmake"
    VERSION "${PCG_CXX_VERSION}"
    COMPATIBILITY SameMinorVersion
  )

  install(TARGETS PCG_CXX
          EXPORT PCG_CXXTargets
          LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
          ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
          RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
          INCLUDES DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
  )

  install(FILES "${CMAKE_CURRENT_SOURCE_DIR}/include/pcg_random.hpp"
                "${CMAKE_CURRENT_SOURCE_DIR}/include/pcg_extras.hpp"
                "${CMAKE_CURRENT_SOURCE_DIR}/include/pcg_uint128.hpp"
          DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})

  install(EXPORT PCG_CXXTargets
          FILE PCG_CXXTargets.cmake
          NAMESPACE PCG::
          DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/PCG_CXX
  )

  install(FILES
          "${CMAKE_CURRENT_BINARY_DIR}/PCG_CXXConfig.cmake"
          "${CMAKE_CURRENT_BINARY_DIR}/PCG_CXXConfigVersion.cmake"
          DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/PCG_CXX
  )
endif()
