add_library(libext INTERFACE)

add_subdirectory(igl)

# this must be done or else the preprocessor definitions 
# made in IGL's cmake project will not propagate to our library
get_directory_property(igl_defs DIRECTORY igl COMPILE_DEFINITIONS )
target_compile_definitions(IGLLibrary INTERFACE ${igl_defs})

if (NOT EMSCRIPTEN)
  add_subdirectory(igl/third-party/deps/src/glfw "glfw")
  target_link_libraries(IGLLibrary PUBLIC glfw)
endif()


target_link_libraries(libext INTERFACE IGLLibrary)