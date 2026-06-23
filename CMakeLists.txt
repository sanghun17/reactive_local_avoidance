cmake_minimum_required(VERSION 3.0.2)
project(local_avoidance)

add_compile_options(-std=c++14)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  sensor_msgs
  geometry_msgs
  nav_msgs
  std_msgs
  mavros_msgs
  tf
  pcl_ros
  pcl_conversions
)

find_package(PCL REQUIRED)

catkin_package(
  CATKIN_DEPENDS roscpp sensor_msgs geometry_msgs nav_msgs std_msgs mavros_msgs tf pcl_ros pcl_conversions
)

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${PCL_INCLUDE_DIRS}
)

add_executable(Local_Avoidance_SH src/Local_Avoidance_SH.cpp)
target_link_libraries(Local_Avoidance_SH
  ${catkin_LIBRARIES}
  ${PCL_LIBRARIES}
)
