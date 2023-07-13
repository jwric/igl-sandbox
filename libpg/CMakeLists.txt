add_library(
    libpg
    src/libpg.cpp
    src/triangle.cpp
)

if(MSVC)
  add_definitions(-D_CONSOLE)
endif()

if(WIN32)
  add_definitions("-DVK_USE_PLATFORM_WIN32_KHR=1")
  add_definitions("-DNOMINMAX")
endif()

target_include_directories(libpg PUBLIC include)

add_subdirectory(extern)

target_link_libraries(libpg PRIVATE libext)