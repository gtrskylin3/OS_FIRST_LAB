# | Сборка`loadgen` с общей библиотекой |
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra

LIB=../../build/lib/libcommon.a 
IDIR1 = . 
IDIR2 = ../../include 
OBJS = main.o stats.o 
DEPS = $(OBJS:.o=.d)
DEPFLAGS = -MMD -MP 

all: loadgen

loadgen: main.o stats.o $(LIB)
	$(CC) $(OBJS) $(LIB) -o loadgen

main.o: main.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR1) -I$(IDIR2) -c main.c -o $@

stats.o: stats.c
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR1) -I$(IDIR2) -c stats.c -o $@

-include $(DEPS)

clean:
	rm -f loadgen $(DEPS) $(OBJS) 

