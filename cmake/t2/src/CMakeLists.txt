cmake_minimum_required(VERSION 2.8)

ADD_EXECUTABLE(hello main.c)
# 指定生成的二进制文件存放到build目录下的bin
SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
# 指定生成的库文件的存放位置
# SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)
