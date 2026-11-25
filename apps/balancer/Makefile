# Сборка `balancer` с общей библиотекой |
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra

LIB=../../build/lib/libcommon.a 
IDIR1 = . 
IDIR2 = ../../include 

all: balancer

balancer: main.c router.c router.h $(LIB)
	$(CC) $(CFLAGS) main.c router.c -I$(IDIR1) -I$(IDIR2) $(LIB) -o balancer

clean:
	rm -f balancer 
