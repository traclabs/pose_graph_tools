cmake_minimum_required(VERSION 2.8.3)
project(pose_graph_tools)

find_package(catkin_simple REQUIRED)

catkin_simple() #catkin_simple(ALL_DEPS_REQUIRED) No needed, yay
add_definitions(-std=c++11) #-Wall

cs_add_library(${PROJECT_NAME}
  src/visualizer.cpp
)

cs_add_executable(visualizer_node
  src/visualizer_node.cpp
#  src/visualizer.cpp
)

target_link_libraries(visualizer_node ${PROJECT_NAME})

cs_install()
cs_export()


