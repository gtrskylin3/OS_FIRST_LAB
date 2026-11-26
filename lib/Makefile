# Сборка статической библиотеки `libcommon.a`
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra
IDIR = ../include
LIBDIR = ../build/lib

DEPFLAGS = -MMD -MP
OBJS = http.o net.o utils.o 
DEPS = $(OBJS:.o=.d)

all: $(LIBDIR)/libcommon.a

$(LIBDIR)/libcommon.a: $(OBJS)
	mkdir -p $(LIBDIR)
	ar rcs $@  $^

http.o: http.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR) -c http.c -o $@
	
net.o: net.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR) -c net.c -o $@
	
utils.o: utils.c 
	$(CC) $(CFLAGS) $(DEPFLAGS) -I$(IDIR) -c utils.c -o $@

-include $(DEPS)

clean:
	rm -f $(LIBDIR)/libcommon.a
	rm -f $(OBJS) $(DEPS)
