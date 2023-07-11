add_executable(
    pg
    src/main.cpp
)

target_link_libraries(pg PRIVATE libpg)

if(EMSCRIPTEN)
    set_target_properties(pg PROPERTIES LINK_FLAGS "-s WASM=1 -s USE_WEBGL2=1 -s USE_GLFW=3" SUFFIX .html)
endif()
