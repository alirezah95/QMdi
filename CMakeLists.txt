cmake_minimum_required(VERSION 3.22)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

find_package(QT NAMES Qt6 Qt5)

set(PROJECT_NAME "QMdi")
set(PROJECT_VERSION_MAJOR 1)
set(PROJECT_VERSION_MINOR 0)
set(PROJECT_VERSION_PATCH 1)
set(PROJECT_VERSION_TWEAK 0)
if (PROJECT_VERSION_TWEAK EQUAL 0)
    set(PROJECT_VERSION ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH})
else()
    set(PROJECT_VERSION ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH}.${PROJECT_VERSION_TWEAK})
endif()
set(PROJECT_VERSION_TYPE "alpha")
set(PROJECT_LICENSE_TYPE "MIT")
set(PROJECT_CREATOR "Alireza")
set(PROJECT_LANGUAGES "C++ QML")
set(PROJECT_DESCRIPTION "A module providing the ability to easily use Material Design Icons Font in Qml elements")
set(PROJECT_HOMEPAGE_URL "https://github.com/alirezah95/QMdi")

project(${PROJECT_NAME}
    VERSION ${PROJECT_VERSION}
    DESCRIPTION ${PROJECT_DESCRIPTION}
    HOMEPAGE_URL ${PROJECT_HOMEPAGE_URL}
    LANGUAGES CXX
)

if(QT_VERSION_MAJOR EQUAL 6)
    set_source_files_properties(ui/qml/Mdi.qml PROPERTIES
        QT_QML_SINGLETON_TYPE TRUE
    )

    qt_add_qml_module(${PROJECT_NAME}
        URI ${PROJECT_NAME}
        VERSION 1.0
        SHARED
        RESOURCES
            ui/resources/materialdesignicons-webfont.ttf
            ui/qml/qmldir
        QML_FILES
            ui/qml/Mdi.qml
    )
endif()
