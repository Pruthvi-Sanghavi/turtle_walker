cmake_minimum_required(VERSION 2.8.3)
project(turtle_walker)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  message_generation
  tf
)



generate_messages(
 DEPENDENCIES
 std_msgs
)


catkin_package()

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)





add_executable(walker src/main.cpp src/turtle_walker.cpp)
target_link_libraries(walker ${catkin_LIBRARIES})





