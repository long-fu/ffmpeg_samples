cmake_minimum_required(VERSION 3.0.0)
project(main VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

include_directories(
    ./inc/
    /usr/local/include/
    /usr/local/cuda-12.1/include/
)

# add host lib path
# link_directories(

# )

add_executable(main main.c)
target_link_libraries(main stdc++ pthread avcodec avutil swscale avformat avcodec avformat avdevice avutil swresample avfilter swscale nvcuvid nvidia-encode)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
