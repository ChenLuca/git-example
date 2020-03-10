cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

add_definitions(-std=c++11)

project(passthrough)

find_package(PCL 1.2 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

add_executable (../exe/pcd_read 1.pcd_read/pcd_read.cpp)
target_link_libraries (../exe/pcd_read ${PCL_LIBRARIES})

add_executable (../exe/pcd_write 2.pcd_write/pcd_write.cpp)
target_link_libraries (../exe/pcd_write ${PCL_LIBRARIES})

add_executable (../exe/concatenate_clouds 3.concatenate_clouds/concatenate_clouds.cpp)
target_link_libraries (../exe/concatenate_clouds ${PCL_LIBRARIES})

add_executable (../exe/narf_keypoint_extraction 4.narf_keypoint_extraction/narf_keypoint_extraction.cpp)
target_link_libraries (../exe/narf_keypoint_extraction ${PCL_LIBRARIES})

add_executable (../exe/range_image_visualization 5.range_image_visualization/range_image_visualization.cpp)
target_link_libraries (../exe/range_image_visualization ${PCL_LIBRARIES})
