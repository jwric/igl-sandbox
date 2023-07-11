add_library(
    libpg
    src/libpg.cpp
)

target_include_directories(libpg PUBLIC include)

add_subdirectory(extern)

target_link_libraries(libpg libext)