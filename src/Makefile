BOARD_FQBN = MiniCore:avr:8
PORT = /dev/ttyUSB0
SKETCH = 702_MAX6675_solder_station/702_MAX6675_solder_station.ino
BUILD_DIR = ./build

# ATmega8
MCU = atmega8
F_CPU = 8000000L
LFUSE = 0xE4
HFUSE = 0xDA

compile:
	./arduino-cli compile \
	--fqbn $(BOARD_FQBN) \
	--board-options "clock=8MHz_internal" \
	--build-property "compiler.cpp.extra_flags=-D__AVR_ATmega8__ -DF_CPU=$(F_CPU)" \
	--build-path $(BUILD_DIR) \
	$(SKETCH)

upload:
	./arduino-cli upload \
	-p $(PORT) \
	--fqbn $(BOARD_FQBN) \
	--board-options "clock=8MHz_internal" \
	--input-dir $(BUILD_DIR)

clean:
	rm -rf $(BUILD_DIR)

.PHONY: compile upload clean
