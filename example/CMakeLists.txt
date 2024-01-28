cmake_minimum_required(VERSION 3.16)
project(apriltag VERSION 3.3.0 LANGUAGES C CXX)

# opencv_demo
set(AprilTag_DIR /home/lizhang/AiGuan_Projects/camera_cal_deeplearning/ApirlTag3CPP) # 将这部分的路径改成自己的

include_directories(${AprilTag_DIR}/include)

# opencv_demo 该软件需要使用到opencv
find_package(OpenCV)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(opencv_demo example.cpp)

target_link_libraries(opencv_demo
                      ${AprilTag_DIR}/lib/libapriltag.so.3
                      ${OpenCV_LIBRARIES}
                    )
