cmake_minimum_required(VERSION 3.4)

# ============================================================================================
# VCPKG Toolchain
# ============================================================================================
if(WIN32)
    # use vcpkg as packages manager in windows platform
    # environment variable needs to be added for the path to vcpkg installation "VCPKG_ROOT"
    set(CMAKE_TOOLCHAIN_FILE "$ENV{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake")
endif(WIN32)

# ============================================================================================
# ============================================================================================
set(CMAKE_FIND_PACKAGE_PREFER_CONFIG ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_INSTALL_PREFIX ${CMAKE_CURRENT_SOURCE_DIR}/build/package)
set(CMAKE_CXX_STANDARD 11)

project(kalman_filter)

enable_language(C CXX)

find_package(Eigen3 3.3 REQUIRED NO_MODULE)

add_subdirectory(KalmanFilter)
add_subdirectory(Examples)
