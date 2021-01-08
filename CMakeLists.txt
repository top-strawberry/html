#
#   create by Strawberry 2020.06.03
#

#cmake 最低版本设置
cmake_minimum_required(VERSION 3.5)

# 指定项目的名称，一般和项目的文件夹名称对应
project(K37A)

# 定义宏
#add_definitions(-DDEV_THINKER_PRO)

# 定义变量
set(CMAKE_CXX_STANDARD 11)
set(PROJECT_NAME WEB)
set(TOP_DIR web)
set(SRC_CODE_DIR ${TOP_DIR}/srcCode/)

# C99编译
set(CMAKE_C_FLAGS "--std=gnu99 ${CMAKE_C_FLAGS}")

# 设置头文件查找路径
#include_directories(V3.0.0/include)

# 设置源文件查找路径
#set(SOURCE_FILES
#    srcCode/main.c
#)

# 发现一个目录下所有的头文件并将列表存储在一个变量中
include_directories(web/cgic SOURCE_FILES)
include_directories(web/html SOURCE_FILES)
include_directories(web/src SOURCE_FILES)

# 发现一个目录下所有的源代码文件并将列表存储在一个变量中
aux_source_directory(web/cgic SOURCE_FILES)
aux_source_directory(web/html SOURCE_FILES)
aux_source_directory(web/src SOURCE_FILES)

message(SOURCE_FILES)

add_executable(${PROJECT_NAME} ${SOURCE_FILES})


#set(PLUG_TEST
#    src/plug/plug_test.c
#    src/plug/plug_packet.c
#    src/plug/plug_packet.h
#)
#add_executable(test_plug ${PLUG_TEST})
#target_link_libraries(test_plug wsock32)