cmake_minimum_required (VERSION 3.15)
project(imgui)
if(POLICY CMP0079)
  cmake_policy(SET CMP0091 NEW)
endif()
if(POLICY CMP0079)
  cmake_policy(SET CMP0079 NEW)
endif()

file(GLOB IMGUI_SRC "*.cpp")


add_library(imgui OBJECT ${IMGUI_SRC} examples/imgui_impl_opengl3.cpp examples/imgui_impl_glfw.cpp)
set_target_properties(imgui PROPERTIES FOLDER "Dependencies/imgui")
set_property(TARGET imgui PROPERTY MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>DLL")
