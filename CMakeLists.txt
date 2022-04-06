cmake_minimum_required(VERSION 3.0.2)
project(vehicle_distance)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  autoware_msgs
  tf
)

find_package(PythonLibs 2.7) #matplot
## Generate messages in the 'msg' folder
# add_message_files(
#   FILES
#   Message1.msg
#   Message2.msg
# )

## Generate services in the 'srv' folder
# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

## Generate added messages and services with any dependencies listed here
# generate_messages(
#   DEPENDENCIES
#   std_msgs
# )

catkin_package(
  CATKIN_DEPENDS autoware_msgs roscpp rospy std_msgs tf
)

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${PYTHON_INCLUDE_DIRS}#matplot
)


include_directories("/home/meclab/catkin_ws/src/matplotlib-cpp/")#matplot

add_executable(vehicle_distance src/vehicle_distance.cpp)
target_link_libraries(vehicle_distance ${catkin_LIBRARIES} ${PYTHON_LIBRARIES})#matplot
