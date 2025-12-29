# ロジック部分を "TripPlanCore" という名前のライブラリにする
qt_add_library(TripPlanCore STATIC
    # ここにC++のソースファイルを追加していく
    TripModel.cpp
    TripModel.h
    # 将来、API通信クラスなどもここに追加
)

# QtのCore機能を使うことを宣言
target_link_libraries(TripPlanCore PUBLIC Qt6::Core)

# 他のフォルダからこのライブラリのヘッダーを参照できるようにする
target_include_directories(TripPlanCore PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})