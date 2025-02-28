CC = gcc
CFLAGS = -Wall

all: my_program

$(OBJ_MAIN): main.c
	$(CC) $(CFLAGS) -c main.c -o main.o

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

my_program: main.o src1.o src2.o src3.o
	$(CC) main.o src1.o src2.o src3.o -o my_program

clean:
	rm -f *.o my_program
	touch clean

.PHONY: clean
