cmake_minimum_required(VERSION 2.8)

PROJECT (HELLO)
ADD_SUBDIRECTORY(src)

# 普通文件的安装直接copy
INSTALL(FILES COPYRIGHT README DESTINATION share/doc/cmake/t2)
# 脚本的安装
INSTALL(PROGRAMS runhello.sh DESTINATION bin)
# 目录的安装，doc/ 代表将目录中的内容安装到目标路径
INSTALL(DIRECTORY doc/ DESTINATION share/doc/cmake/t2)


