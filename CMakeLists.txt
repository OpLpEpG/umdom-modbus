# CMake file to compile this Modbus component as a west module in Zephyr

if(CONFIG_LIGHTMODBUS_SLAVE_BASE)

message("UMDOM: modul MODBUS Запуск сборки.")

  zephyr_include_directories(
    src/
  )

  zephyr_library()
  zephyr_library_compile_definitions(NO_POSIX_CHEATS)

  file(GLOB_RECURSE MODBUS_SRCS . src/*.c)
  zephyr_library_sources(${MODBUS_SRCS})

endif()
