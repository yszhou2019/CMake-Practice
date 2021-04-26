SET(LIBHELLO_SRC hello.c)
# 制作成动态库和静态库，lib的name是hello
ADD_LIBRARY(hello SHARED ${LIBHELLO_SRC})
ADD_LIBRARY(hello_static STATIC ${LIBHELLO_SRC})
# 设置库的名称
SET_TARGET_PROPERTIES(hello PROPERTIES OUTPUT_NAME "hello")
SET_TARGET_PROPERTIES(hello PROPERTIES CLEAN_DIRECT_OUTPUT 1)
SET_TARGET_PROPERTIES(hello_static PROPERTIES OUTPUT_NAME "hello")
SET_TARGET_PROPERTIES(hello_static PROPERTIES CLEAN_DIRECT_OUTPUT 1)
# VERSION指定动态库的版本,SOVERSION指定API的版本
SET_TARGET_PROPERTIES(hello PROPERTIES VERSION 1 SOVERSION 1)
# 库文件的安装，静态库要用ARCHIVE
INSTALL(TARGETS hello hello_static
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)
# 头文件直接cp，cp到include下的hello下，也就是include/hello/hello.h
INSTALL(FILES hello.h DESTINATION include/hello)

# how to use
# step 1, in dir build, run `cmake -DCMAKE_INSTALL_PREFIX=/usr ..`
# step 2, generate binary file, run `make`
# step 3, install, run `make install`
# [100%] Built target hello_static
# Install the project...
# -- Install configuration: ""
# -- Installing: /usr/lib/libhello.so.1.2
# -- Installing: /usr/lib/libhello.so.1
# -- Installing: /usr/lib/libhello.so
# -- Installing: /usr/lib/libhello.a
# -- Installing: /usr/include/hello/hello.h