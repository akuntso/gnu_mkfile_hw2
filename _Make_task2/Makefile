CC = gcc
CFLAGS = -Wall

OBJ_MAIN = main.o
OBJ_SRC1 = src1.o
OBJ_SRC2 = src2.o
OBJ_SRC3 = src3.o

all: my_program

$(OBJ_MAIN): main.c
    $(CC) $(CFLAGS) -c main.c -o $(OBJ_MAIN)

ifeq ($(MAKE_METHOD), include)
include make1.mk
include make2.mk
include make3.mk
else
$(OBJ_SRC1):
    $(MAKE) -f make1.mk

$(OBJ_SRC2):
    $(MAKE) -f make2.mk

$(OBJ_SRC3):
    $(MAKE) -f make3.mk
endif

my_program: $(OBJ_MAIN) $(OBJ_SRC1) $(OBJ_SRC2) $(OBJ_SRC3)
    $(CC) $(OBJ_MAIN) $(OBJ_SRC1) $(OBJ_SRC2) $(OBJ_SRC3) -o my_program

clean:
    rm -f *.o my_program
    touch clean

.PHONY: clean