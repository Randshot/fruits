if(TARGET fruits_rosaceae)
  add_library(fruits::fruits_rosaceae ALIAS fruits_rosaceae)
else()
  # For the real project 'hunter_add_package' should be called before:
  # hunter_add_package(fruits)

  find_package(fruits CONFIG REQUIRED)
endif()

add_executable(fruits_quick_meal ${FRUITS_QUICK_MEAL_SOURCES})
target_link_libraries(fruits_quick_meal PUBLIC fruits::fruits_rosaceae)
