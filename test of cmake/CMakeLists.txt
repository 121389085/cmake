# CMake 最低版本号要求

cmake_minimum_required(VERSION 3.0)
# CMake 设置项目名称
project(Test)

# 设置makefile生成的可执行文件存放路径
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/build)

aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR}/src SRC)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

set(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib)

# 指定生成目标
add_executable(Test ${SRC})
# 添加链接库
add_library(Test_lib1 STATIC ${SRC})
add_library(Test_lib2 SHARED ${SRC})