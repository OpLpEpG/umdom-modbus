
zephyr_include_directories_ifdef(CONFIG_USE_MODBUS 
include 
src)

zephyr_sources_ifdef(CONFIG_USE_MODBUS
	src/lightmodbus.c 
	src/scoils.c 
	src/slave.c 
	src/sregs.c 
)
