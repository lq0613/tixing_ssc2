# 设置 CMake 的最低版本要求
cmake_minimum_required(VERSION 3.10)

# 设置项目名称
project(Btraj)

# 设置可执行文件的输出目录
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# 添加可执行文件，将源代码文件添加到这里
add_executable(Btraj 
    src/cub_extend_3d.cc
    src/cub_wrapper.cpp
    src/cuboid_3d.cc
    src/piecewise_jerk_problem.cc
    #src/solve_3d.cc
    # 添加你的其他源文件
)
# 如果有其他依赖，比如库文件，可以在这里添加

target_link_libraries(Btraj
 osqp.so
)

# 设置编译选项，比如 C++ 标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 如果需要其他特定的编译选项，可以在这里添加
# add_compile_options(-Wall -Wextra)

# 添加头文件搜索路径
include_directories(include)
include_directories(${GLOG_INCLUDE_DIRS})
# 添加子目录，如果有其他子目录包含源文件
# add_subdirectory(subdirectory_name)

# 可以根据需要添加其他配置


