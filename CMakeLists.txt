cmake_minimum_required(VERSION 3.0.0)
project(main VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

# 指定头文件搜索位置
include_directories(
    ./inc/
    /usr/local/include/
    /usr/local/cuda/include/
)

# add host lib path 手动指定 在那里搜索 lib包
link_directories(
    /usr/local/lib/
)

add_executable(main main_hw_de.c)
target_link_libraries(main stdc++ pthread avcodec avformat avdevice avutil swresample avfilter swscale nvcuvid nvidia-encode)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
