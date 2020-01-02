
# SPDX-License-Identifier: Apache-2.0

# CMake file to compile this Modbus component as a west module in Zephyr

if(CONFIG_USE_MODBUS)

#if (NOT DEFINED ENV{BSIM_COMPONENTS_PATH})
#  message(FATAL_ERROR "This Zephyr module requires the BabbleSim simulator.\
#Please set the  environment variable BSIM_COMPONENTS_PATH to point to its\
#components folder. More information can be found in\
#https://babblesim.github.io/folder_structure_and_env.html")
#endif()
#if (NOT DEFINED ENV{BSIM_OUT_PATH})
#  message(FATAL_ERROR "This Zephyr module requires the BabbleSim simulator.\
#Please set the  environment variable BSIM_OUT_PATH to point to the folder\
#where the simulator is compiled to. More information can be found in\
#https://babblesim.github.io/folder_structure_and_env.html")
#endif()

  zephyr_include_directories(
    src/
  )

  zephyr_library()
  zephyr_library_compile_definitions(NO_POSIX_CHEATS)

  file(GLOB_RECURSE MODBUS_SRCS . src/*.c)
  zephyr_library_sources(${MODBUS_SRCS})

endif()
