# | Сборка`loadgen` с общей библиотекой |
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra

LIB=../../build/lib/libcommon.a 
IDIR1 = . 
IDIR2 = ../../include 

all: loadgen

loadgen: main.c stats.c stats.h $(LIB)
	$(CC) $(CFLAGS) main.c stats.c -I$(IDIR1) -I$(IDIR2) $(LIB) -o loadgen

clean:
	rm -f loadgen 

