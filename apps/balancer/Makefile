# Сборка `balancer` с общей библиотекой |
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra

LIB=../../build/lib/libcommon.a 
IDIR1 = . 
IDIR2 = ../../include 

DEPFLAGS = -MMD -MP 
OBJS = main.o router.o 
DEPS = $(OBJS:.o=.d)

all: balancer

balancer: $(OBJS) $(LIB)
	$(CC) $(OBJS) $(LIB) -o balancer

main.o: main.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR1) -I$(IDIR2) -c main.c -o $@
	
router.o: router.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR1) -I$(IDIR2) -c router.c -o $@	


-include $(DEPS)

clean:
	rm -f balancer $(OBJS) $(DEPS)
