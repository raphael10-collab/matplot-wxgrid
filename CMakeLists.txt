cmake_minimum_required(VERSION 3.5)
project(Grid)


find_package(wxWidgets REQUIRED COMPONENTS base core webview stc xml richtext aui)
include(${wxWidgets_USE_FILE})

include(FetchContent)

find_package(PkgConfig REQUIRED)

find_package(Matplot++ REQUIRED)

link_libraries(${wxWidgets_LIBRARIES})

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


add_executable(${PROJECT_NAME}
    griddemo.cpp
)

target_link_libraries( ${PROJECT_NAME} PUBLIC
    wxWidgets::wxWidgets
    Matplot++::matplot
)
