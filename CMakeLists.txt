cmake_minimum_required(VERSION 2.8.3)
project(driving_simulator_msgs)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  diagnostic_msgs 
  message_generation
)

add_message_files(
   FILES
   Waypoint.msg
   Traj.msg
   Belief.msg
   State.msg
   Action.msg
)

## Generate added messages and services with any dependencies listed here
generate_messages(
   DEPENDENCIES
   std_msgs  # Or other packages containing msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES driving_simulator
  CATKIN_DEPENDS message_runtime std_msgs
#  DEPENDS system_lib
)

install(DIRECTORY include/${PROJECT_NAME}/
        DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION})