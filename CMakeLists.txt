cmake_minimum_required(VERSION 2.8.3)
project(camera_info_manager_py)

find_package(catkin REQUIRED COMPONENTS rospy sensor_msgs)
include_directories(include ${catkin_INCLUDE_DIRS})

catkin_python_setup()
catkin_package(CATKIN_DEPENDS sensor_msgs)

if (CATKIN_ENABLE_TESTING)
  add_subdirectory(tests)
endif(CATKIN_ENABLE_TESTING)
