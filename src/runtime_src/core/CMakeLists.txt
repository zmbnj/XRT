include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  )

add_subdirectory(include)
 if (${XRT_NATIVE_BUILD} STREQUAL "yes")
   add_compile_options("-DXRT_CORE_BUILD_WITH_DL")
   add_subdirectory(common)
   add_subdirectory(pcie)
   add_subdirectory(tools)
 else()
   add_compile_options("-DXRT_CORE_BUILD_WITH_DL")
   add_subdirectory(common)
   add_subdirectory(edge)
   add_subdirectory(tools)
 endif()
