cmake_minimum_required(VERSION 3.20)
project(minkindr)
find_package(ament_cmake REQUIRED)
find_package(ament_cmake_gtest REQUIRED)
find_package(Eigen3 REQUIRED)
find_package(glog 0.6.0 REQUIRED)
find_package(Threads)
INCLUDE_DIRECTORIES ( "${EIGEN3_INCLUDE_DIR}" )

# Add all files to show up in QtCreator.
FILE(GLOB_RECURSE LibFiles "include/*")
add_custom_target(headers SOURCES ${LibFiles})

ament_export_include_directories(include ${EIGEN3_INCLUDE_DIR})

ament_package()

install(
  DIRECTORY include/
  DESTINATION include
)