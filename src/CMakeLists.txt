add_subdirectory(core)

# 実行ファイルの定義
qt_add_executable(appTripPlan
    main.cpp
)

# QMLモジュールの定義
qt_add_qml_module(appTripPlan
    URI TripPlan
    VERSION 1.0
    RESOURCE_PREFIX "/"
    QML_FILES
        ui/Main.qml
        # ui/pages/MapPage.qml など増えたらここに追加
)

# ②で作ったロジックライブラリ(TripPlanCore)とリンクする
target_link_libraries(appTripPlan
    PRIVATE Qt6::Quick
    PRIVATE TripPlanCore 
)

# インストール設定（配布用）
include(GNUInstallDirs)
install(TARGETS appTripPlan
    BUNDLE DESTINATION .
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
