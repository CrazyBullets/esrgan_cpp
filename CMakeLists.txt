# 指定 CMake 的最小版本
cmake_minimum_required(VERSION 3.10)

# 设置项目名称和版本
project(MyProject)

# 查找 OpenCV 版本
# set(OpenCV_DIR "C:/MyLibrary/OpenCV/opencv4_5_4_bin")
find_package(OpenCV REQUIRED)
link_directories(${OpenCV_INCLUDE_DIRS})

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)







# 添加可执行文件
add_executable(my_executable main.cc utils.cc)



# 链接 OpenCV 库
target_link_libraries(my_executable ${OpenCV_LIBS})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PACKAGE_VERSION ${PROJECT_VERSION})


