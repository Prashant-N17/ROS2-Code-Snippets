cmake_minimum_required(VERSION 3.5)
project(basics)

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)

set(dependencies
  rclcpp
)

add_executable(simple src/simple.cpp)
ament_target_dependencies(simple ${dependencies})

//add the executables and ament_target_dependencies as per the programs 
//you want to build

//add install instructions with all the executibles.

install(TARGETS
  simple
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION lib/${PROJECT_NAME}
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_export_dependencies(${dependencies})
ament_package()
