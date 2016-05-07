# Syntax for this file: https://cmake.org/cmake/help/v2.8.12/cmake.html
# Reference manual: http://doc.qt.io/qt-5/cmake-manual.html

cmake_minimum_required(VERSION 2.8.12)
# 2.8.11 is required for automatic linking to the qtmain.lib library on Windows

project(example-project CXX)

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)

# Instruct CMake to run moc/resource/ui automatically when needed.
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

# Find the QtWidgets library
find_package(Qt5Widgets REQUIRED)

# Tell CMake to create the example-project executable
add_executable(${CMAKE_PROJECT_NAME} WIN32
    src/main.cpp
    src/mainwindow.cpp
    resources/resources.qrc)

# Use the Widgets module from Qt 5.
target_link_libraries(${CMAKE_PROJECT_NAME} Qt5::Widgets)
