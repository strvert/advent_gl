cmake_minimum_required(VERSION 3.12)

# プロジェクト名の設定
project(advent_gl)

# 必須ライブラリの存在チェック
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)

# glad関係
include_directories(glad/include)
add_subdirectory(glad)

# コンパイルオプション
add_compile_options(-O2 -Wall)

# 実行ファイルの指定
add_executable(advent_gl main.cpp)

# 実行ファイルにリンクするライブラリの指定
target_link_libraries(advent_gl glad glfw glm ${CMAKE_DL_LIBS})

# c++17を使う
set_property(TARGET advent_gl PROPERTY CXX_STANDARD 17)
