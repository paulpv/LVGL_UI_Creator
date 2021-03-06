cmake_minimum_required(VERSION 3.0.0)

file(GLOB_RECURSE UICreator_SRC
    "*.h"
    "*.cpp"
)

set(CXX g++-8)
set(cc gcc-8)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_EXTENSIONS ON)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(../3rdParty/LVGL)
include_directories(../3rdParty/LVGL/lvgl)
include_directories(../3rdParty/freetype-2.10.1/include)
include_directories(../3rdParty/spdlog-1.x/include)
include_directories(../LVSerial)

add_executable(UICreator ${UICreator_SRC})


link_directories(LVSerial)
link_directories(3rdParty/LVGL)
link_directories(3rdParty/freetype-2.10.1)
target_link_libraries(UICreator freetype)
target_link_libraries(UICreator LVGL)
target_link_libraries(UICreator freetype)
target_link_libraries(UICreator LVSerial)
target_link_libraries(UICreator libstdc++fs.a)