cmake_minimum_required(VERSION 2.8.3)
project(fetch_teleop)

find_package(Boost REQUIRED)
find_package(catkin REQUIRED
  COMPONENTS
    actionlib
    control_msgs
    geometry_msgs
    roscpp
    sensor_msgs
    topic_tools
)
catkin_package()

include_directories(
  ${Boost_INCLUDE_DIRS}
  ${catkin_INCLUDE_DIRS}
)

add_executable(joystick_teleop src/joystick_teleop.cpp)
target_link_libraries(joystick_teleop
  ${Boost_LIBRARIES}
  ${catkin_LIBRARIES}
)

install(
  TARGETS joystick_teleop
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)