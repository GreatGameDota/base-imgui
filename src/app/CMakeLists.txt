add_executable(
  base-imgui
  main.cpp 
  ../${IMGUI_PATH}/imgui.cpp 
  ../${IMGUI_PATH}/imgui_demo.cpp
  ../${IMGUI_PATH}/imgui_draw.cpp 
  ../${IMGUI_PATH}/imgui_tables.cpp
  ../${IMGUI_PATH}/imgui_widgets.cpp
  ../${IMGUI_PATH}/backends/imgui_impl_sdl2.cpp
  ../${IMGUI_PATH}/backends/imgui_impl_vulkan.cpp 
  ../${IMPLOT_PATH}/implot.cpp 
  ../${IMPLOT_PATH}/implot_items.cpp 
  ../${IMPLOT_PATH}/implot_demo.cpp 
)

target_include_directories(
  base-imgui PUBLIC
  ../lib/imgui
  ../lib/imgui/backends
  ../lib/implot
  ${SDL2_INCLUDE_DIRS}
  ${Vulkan_INCLUDE_DIRS}
)

target_link_libraries(
  base-imgui
  ImGui 
  ImPlot
  ${SDL2_LIBRARIES}
  ${Vulkan_LIBRARIES}
)

add_custom_command(TARGET base-imgui POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy_if_different $<TARGET_FILE:SDL2::SDL2> $<TARGET_FILE_DIR:base-imgui>
)

# No console window for non-debug builds
set_target_properties(base-imgui PROPERTIES WIN32_EXECUTABLE
  $<AND:$<PLATFORM_ID:Windows>,$<NOT:$<CONFIG:Debug,RelWithDebInfo>>>
)