cmake_minimum_required(VERSION 2.8.3)
project(lma_kinematics_plugin)

find_package(Boost REQUIRED system filesystem date_time program_options signals thread)
find_package(catkin REQUIRED COMPONENTS
  moveit_core
  cmake_modules
  pluginlib
  actionlib
  dynamic_reconfigure
)

find_package(Eigen REQUIRED)

catkin_package(
  INCLUDE_DIRS
    include
  CATKIN_DEPENDS
    pluginlib
    moveit_core
)

include_directories(include)
include_directories(${catkin_INCLUDE_DIRS})
include_directories(SYSTEM ${EIGEN_INCLUDE_DIRS} ${Boost_INCLUDE_DIRS})

set(MOVEIT_LIB_NAME moveit_lma_kinematics_plugin)

add_library(${MOVEIT_LIB_NAME} src/lma_kinematics_plugin.cpp 
  src/chainiksolver_pos_lma_jl_mimic.cpp 
  src/chainiksolver_vel_pinv_mimic.cpp)

target_link_libraries(${MOVEIT_LIB_NAME} ${catkin_LIBRARIES})

install(TARGETS ${MOVEIT_LIB_NAME} LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})
install(DIRECTORY include/ DESTINATION include)

install(
  FILES
    lma_kinematics_plugin_description.xml
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION})
