add_library(libext INTERFACE)

add_subdirectory(igl)
add_compile_options("-DIGL_WITH_SAMPLES=OFF")

target_link_libraries(libext INTERFACE IGLLibrary)