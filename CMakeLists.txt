cmake_minimum_required(VERSION 3.13.0)

get_filename_component(ProjectId ${CMAKE_CURRENT_LIST_DIR} NAME)
string(REPLACE " " "_" ProjectId ${ProjectId})

project(${ProjectId} VERSION 0.1.0)

include(CTest)

enable_testing()

add_executable(${PROJECT_NAME} main.cpp)

link_directories(/usr/bin)
#link_directories(/home/sean/projects/accelerometer-test/build/lib/)
target_link_libraries(${PROJECT_NAME} gpiod)
target_link_libraries(${PROJECT_NAME} i2c)

#target_link_libraries(${PROJECT_NAME} MPU6050.h)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)