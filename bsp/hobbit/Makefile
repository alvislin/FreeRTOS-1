BUILDDIR= ../../build
SRC= $(wildcard *.c)
OBJ= $(SRC:.c=.o)
TAR = bsp.a
INC_DIR	= ../../include
INC1_DIR = ../../freertosv8.2.3/FreeRTOS

CFLAGS += -I$(INC_DIR) \
			-I$(INC_DIR)/$(SOC) \
			-I$(INC_DIR)/csky \
			-I$(INC_DIR)/lib \
			-I$(INC1_DIR)/Source/include \
			-I$(INC1_DIR)/Source/portable/GCC/$(TARGET_CPU)

all: $(TAR)


%.o: %.c
	$(CC) $(CFLAGS) $< -o $@

$(TAR): $(OBJ)
	$(AR) r $(BUILDDIR)/$(TAR) $(OBJ)
#	$(RM) -rf $(OBJ)
	mv $(OBJ) $(BUILDDIR)


clean:
	$(RM) -rf $(BUILDDIR)/*.o
	$(RM) -rf $(BUILDDIR)/*.a
	$(RM) -rf $(BUILDDIR)/*.elf

