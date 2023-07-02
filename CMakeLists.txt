cmake_minimum_required(VERSION 3.10)
project(mpi_enc_test)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include/mpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include/mpp/base)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include/osal)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include/utils)

link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)
file(GLOB_RECURSE utils_src ${CMAKE_CURRENT_SOURCE_DIR}/src/utils/*.c)

add_executable(enc_test_demo 
               src/ctx_manager.c
               src/encode.c
               src/test_demo.c
               ${utils_src}
               )

target_link_libraries(enc_test_demo osal rockchip_mpp dl z stdc++)

