file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS "./*.cpp")
list(REMOVE_ITEM SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/main.cpp")

add_library(
  app
    ${SOURCES}
)

target_include_directories(app PRIVATE ../include)
target_compile_options(app PRIVATE ${SANITIZE_FLAGS})
target_link_options(app PRIVATE ${SANITIZE_FLAGS})
target_link_libraries(app PRIVATE)

add_executable(
  app.elf
    ./main.cpp
)

target_include_directories(app.elf PRIVATE ../include)
target_compile_options(app.elf PRIVATE ${SANITIZE_FLAGS})
target_link_options(app.elf PRIVATE ${SANITIZE_FLAGS})
target_link_libraries(app.elf PRIVATE app)
