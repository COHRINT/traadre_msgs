cmake_minimum_required(VERSION 2.8.3)
project(traadre_msgs)
set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")
find_package(catkin REQUIRED
        COMPONENTS
	    message_generation	
            nav_msgs
	    geometry_msgs
	    std_msgs
        )
	
add_message_files(
  FILES
  Steering.msg
  RobotState.msg
  NamedGoal.msg
  part_id.msg
  GoalComplete.msg
  Callout.msg
  Policy.msg
  OptionSelect.msg
)

add_service_files(
  FILES
  GetGoalList.srv
  SetCurrentGoal.srv
  Teleport.srv
  SetFuelLevel.srv
  ShowToast.srv
  GetMCSims.srv
  GetPaths.srv
)

#catkin_python_setup()

generate_messages(
  DEPENDENCIES
  nav_msgs
  geometry_msgs
  std_msgs
)

catkin_package(
    INCLUDE_DIRS
    LIBRARIES ${PROJECT_NAME}
    CATKIN_DEPENDS
	geometry_msgs
        nav_msgs
	std_msgs
	message_runtime
)

