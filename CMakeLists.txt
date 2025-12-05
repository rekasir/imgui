enable_language(CXX)

add_library(
  imgui
  imgui.cpp
  imgui_demo.cpp
  imgui_draw.cpp
  imgui_tables.cpp
  imgui_widgets.cpp
  backends/imgui_impl_sdl3.cpp
  backends/imgui_impl_sdlrenderer3.cpp
  misc/freetype/imgui_freetype.cpp
  cimgui/cimgui.cpp
  cimgui/cimgui_internal.cpp)
target_include_directories(
  imgui
  PUBLIC .)
target_link_libraries(
  imgui
  PRIVATE SDL3::SDL3 freetype stdc++)
target_compile_definitions(
  imgui
  PUBLIC IMGUI_ENABLE_FREETYPE=1 IMGUI_IMPL_API=extern\t\"C\"\t)

set_target_properties(
  imgui
  PROPERTIES CXX_STANDARD 11 CXX_STANDARD_REQUIRED ON)
