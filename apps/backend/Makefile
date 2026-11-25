# | Сборка `backend` с общей библиотекой |
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra

LIB=../../build/lib/libcommon.a 
IDIR1 = . 
IDIR2 = ../../include 

all: backend 

backend: main.c handler.c handler.h $(LIB)
	$(CC) $(CFLAGS) main.c handler.c -I$(IDIR1) -I$(IDIR2) $(LIB) -o backend

clean:
	rm -f backend 
