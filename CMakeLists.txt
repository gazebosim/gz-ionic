cmake_minimum_required(VERSION 3.10.2 FATAL_ERROR)

#============================================================================
# Initialize the project
#============================================================================
project(gz-ionic VERSION 1.0.0)

#============================================================================
# Find gz-cmake
#============================================================================
# If you get an error at this line, you need to install gz-cmake
find_package(gz-cmake3 REQUIRED)

#============================================================================
# Configure the project
#============================================================================
gz_configure_project(VERSION_SUFFIX)

# all list of ionic packages

gz_find_package(gz-common5 REQUIRED)
gz_find_package(gz-fuel_tools9 REQUIRED)
gz_find_package(gz-sim8 REQUIRED)
gz_find_package(gz-gui8 REQUIRED)
gz_find_package(gz-launch7 REQUIRED)
gz_find_package(gz-math7 REQUIRED)
gz_find_package(gz-msgs10 REQUIRED)
gz_find_package(gz-physics7 REQUIRED)
gz_find_package(gz-plugin2 REQUIRED)
gz_find_package(gz-rendering8 REQUIRED)
gz_find_package(gz-sensors8 REQUIRED)
gz_find_package(gz-transport13 REQUIRED)
gz_find_package(gz-utils2 REQUIRED)
gz_find_package(sdformat14 REQUIRED)

if(build_warnings)
  set(all_warnings " CONFIGURATION WARNINGS:")
  foreach (msg ${build_warnings})
    gz_string_append(all_warnings " -- ${msg}" DELIM "\n")
  endforeach ()
  message(WARNING "${all_warnings}")
endif (build_warnings)

if(build_errors)
  message(SEND_ERROR "-- BUILD ERRORS: These must be resolved before compiling.")
  foreach(msg ${build_errors})
    message(SEND_ERROR "-- ${msg}")
  endforeach()
  message(SEND_ERROR "-- END BUILD ERRORS\n")

  set(error_str "Errors encountered in build. Please see BUILD ERRORS above.")

  message(FATAL_ERROR "${error_str}")

endif()

install(DIRECTORY gazebodistro DESTINATION ${IGN_DATA_INSTALL_DIR})
