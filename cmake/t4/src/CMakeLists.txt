cmake_minimum_required(VERSION 2.8)

ADD_EXECUTABLE(main main.c)
# 指定lib的头文件的搜索路径
INCLUDE_DIRECTORIES(/usr/include/hello)
# 指定lib的搜索路径
# 动态库有一些莫名其妙的问题，静态库可以正常工作
# TARGET_LINK_LIBRARIES(main libhello.so)
TARGET_LINK_LIBRARIES(main libhello.a)