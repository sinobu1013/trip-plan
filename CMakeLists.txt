cmake_minimum_required(VERSION 3.16)

project(TripPlan VERSION 0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Qtの必須コンポーネントを探す
find_package(Qt6 REQUIRED COMPONENTS Core Quick Test)

# 標準的なプロジェクト設定
qt_standard_project_setup(REQUIRES 6.8)

# サブディレクトリを読み込む
add_subdirectory(src)
