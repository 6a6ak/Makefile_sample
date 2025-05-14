# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -Werror -Iinclude

# Directories
OBJ_DIR = obj
BIN_DIR = bin

# Executable name
PROG = $(BIN_DIR)/main.exe

# Source and object files
# Add your source files here
SRC_FILES = main.c
OBJ = $(patsubst %.c, $(OBJ_DIR)/%.o, $(SRC_FILES))

# Default target
all: $(PROG)

# Link object files to create the executable
$(PROG): $(OBJ) | $(BIN_DIR)
	$(CC) -o $@ $^ $(CFLAGS)

# Compile each source file into an object file
$(OBJ_DIR)/%.o: %.c | $(OBJ_DIR)
	$(CC) -c -o $@ $< $(CFLAGS)

# Create necessary directories
$(OBJ_DIR):
	@if not exist $(OBJ_DIR) mkdir $(OBJ_DIR)

$(BIN_DIR):
	@if not exist $(BIN_DIR) mkdir $(BIN_DIR)

# Clean up build files
clean:
	@if exist $(OBJ_DIR) rmdir /S /Q $(OBJ_DIR)
	@if exist $(PROG) del $(PROG)

# Run the program
run: $(PROG)
	$(PROG)

# Phony targets
.PHONY: all clean run
