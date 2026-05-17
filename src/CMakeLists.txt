# find_package(SDL3 REQUIRED)
# find_package(SDL3_image REQUIRED)
# find_package(SDL3_ttf REQUIRED)

file(GLOB_RECURSE
  SOURCES
    CONFIGURE_DEPENDS "./*.cpp"
)

add_library(
  app
    ${SOURCES}
)

target_include_directories(
  app
  PRIVATE
    ../include
)

target_compile_options(
  app
    PRIVATE
      ${SANITIZE_FLAGS}
)

target_link_options(
  app
    PRIVATE
      ${SANITIZE_FLAGS}
)

target_link_libraries(
  app
    PRIVATE 
)

add_executable(
  app.elf
    ${SOURCES}
)

target_include_directories(
  app.elf
  PRIVATE
    ../include
)

target_compile_options(
  app.elf
    PRIVATE
      ${SANITIZE_FLAGS}
)

target_link_options(
  app.elf
    PRIVATE
      ${SANITIZE_FLAGS}
)

target_link_libraries(
  app.elf
    PRIVATE 
    app
)