# | Сборка `backend` с общей библиотекой |
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra

LIB=../../build/lib/libcommon.a 
IDIR1 = . 
IDIR2 = ../../include 
OBJS = handler.o main.o 

DEPS = $(OBJS:.o=.d)
DEPFLAGS = -MMD -MP 
all: backend 

backend: $(OBJS) $(LIB)
	$(CC) $(OBJS) $(LIB) -o $@ 

handler.o: handler.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR1) -I$(IDIR2) -c handler.c -o $@
main.o: main.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR1) -I$(IDIR2) -c main.c -o $@


-include $(DEPS)

clean:
	rm -f backend $(DEPS) $(OBJS)


