# find_package(SDL3 REQUIRED)
# find_package(SDL3_image REQUIRED)
# find_package(SDL3_ttf REQUIRED)

file(GLOB_RECURSE
  SOURCES
    CONFIGURE_DEPENDS "./*.cpp"
)

add_library(
  ${PROJECT_NAME}
    ${SOURCES}
)

target_include_directories(
  ${PROJECT_NAME}
  PRIVATE
    ../include
)

target_compile_options(
  ${PROJECT_NAME}
    PRIVATE
      ${SANITIZE_FLAGS}
)

target_link_options(
  ${PROJECT_NAME}
    PRIVATE
      ${SANITIZE_FLAGS}
)

target_link_libraries(
  ${PROJECT_NAME}
    PRIVATE 
      # SDL3::SDL3 
      # SDL3_ttf::SDL3_ttf
      # SDL3_image::SDL3_image
)