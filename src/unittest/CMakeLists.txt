include_directories(${CMAKE_SOURCE_DIR}/src/)
include_directories(${CMAKE_SOURCE_DIR}/src/media)

AUX_SOURCE_DIRECTORY(${CMAKE_SOURCE_DIR}/src/media H264_WRAP)

add_definitions("-Wunused-variable")

add_executable(h264_wrap_example h264_wrap_example.cpp ${H264_WRAP})
add_executable(rtmp_server_example rtmp_server_example.cpp ${H264_WRAP})

target_link_libraries(h264_wrap_example log)
target_link_libraries(h264_wrap_example rtmp)
target_link_libraries(rtmp_server_example log)
target_link_libraries(rtmp_server_example rtmp)