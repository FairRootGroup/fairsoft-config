cmake_minimum_required(VERSION 3.0...4.0.1)
project(fairsoft-config VERSION 1.0 LANGUAGES C CXX Fortran)
include(GNUInstallDirs)

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 11)
endif()
if(NOT DEFINED FAIRSOFT_VERSION)
  message(FATAL_ERROR "-DFAIRSOFT_VERSION is required!")
endif()
find_package(ROOT REQUIRED)

configure_file(${PROJECT_NAME} ${CMAKE_BINARY_DIR}/${PROJECT_NAME} @ONLY)
install(PROGRAMS ${CMAKE_BINARY_DIR}/${PROJECT_NAME} DESTINATION ${CMAKE_INSTALL_BINDIR})
