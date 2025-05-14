MCU = atmega328p
F_CPU = 16000000UL
TARGET = main
CC="C:\avr\bin\avr-gcc"
OBJCOPY="C:\avr\bin\avr-objcopy"
CFLAGS = -mmcu=$(MCU) -DF_CPU=$(F_CPU) -Wall -Os -I./drive

SRC = main.c
OBJ = $(SRC:.c=.o)

all: $(TARGET).hex

$(TARGET).hex: $(TARGET).elf
	$(OBJCOPY) -O ihex -R .eeprom $< $@

$(TARGET).elf: $(OBJ)
	$(CC) $(CFLAGS) $^ -o $@

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	del /Q *.o *.elf *.hex 2>nul || exit 0