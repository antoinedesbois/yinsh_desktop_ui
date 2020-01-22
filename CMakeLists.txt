cmake_minimum_required (VERSION 3.1)
project (YinshUI)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Wall -fno-exceptions -fno-rtti")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Wall -fno-exceptions -fno-rtti")

find_package(glfw3 REQUIRED)
find_package(glew REQUIRED)
find_package(OpenGL REQUIRED)

add_executable(YinshUI
  main.cpp
  imgui/examples/imgui_impl_opengl3.cpp 
  imgui/examples/imgui_impl_glfw.cpp 
  imgui/imgui.cpp
  imgui/imgui_draw.cpp 
  imgui/imgui_widgets.cpp 
  imgui/imgui_demo.cpp )

target_include_directories(YinshUI PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(YinshUI PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/imgui)
target_include_directories(YinshUI PRIVATE ${GLEW_INCLUDE_DIR})
target_include_directories(YinshUI PRIVATE ${OPENGL_INCLUDE_DIRS})

target_link_libraries(YinshUI glfw)
target_link_libraries(YinshUI ${GLEW_LIBRARY})
target_link_libraries(YinshUI ${OPENGL_LIBRARIES})
