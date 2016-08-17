# Unit tests use nose, but need rostest to create a ROS environment.
find_package(camera_info_manager REQUIRED)
find_package(roscpp REQUIRED)
find_package(rostest REQUIRED)
find_package(rosunit REQUIRED)

# Test camera calibration YAML file compatibility with the C++
# camera_info_manager
add_executable(generate_camera_info generate_camera_info.cpp)
target_link_libraries(generate_camera_info
  ${camera_info_manager_LIBRARIES}
  ${catkin_LIBRARIES}
  ${roscpp_LIBRARIES})

add_rostest(load_cpp_camera_info.test DEPENDENCIES generate_camera_info)
add_rostest(unit_test.test)
