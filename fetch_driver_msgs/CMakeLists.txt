cmake_minimum_required(VERSION 2.8.3)
project(fetch_driver_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    actionlib
    actionlib_msgs
    message_generation
    power_msgs
    std_msgs
)

add_action_files(
  FILES
    DisableCharging.action
)

add_message_files(
  FILES
    BoardState.msg
    JointState.msg
    GripperState.msg
    MotorState.msg
    RobotState.msg
    ChargerState.msg
)

generate_messages(DEPENDENCIES actionlib_msgs power_msgs std_msgs)

catkin_package(
  CATKIN_DEPENDS
    actionlib
    actionlib_msgs
    message_runtime
    power_msgs
    std_msgs
)
