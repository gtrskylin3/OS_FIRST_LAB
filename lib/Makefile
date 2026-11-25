# Сборка статической библиотеки `libcommon.a`
.PHONY: all clean
CC ?= gcc
CFLAGS ?= -Wall -Wextra
IDIR = ../include
LIBDIR = ../build/lib

all: $(LIBDIR)/libcommon.a

$(LIBDIR)/libcommon.a: http.o net.o utils.o
	mkdir -p $(LIBDIR)
	ar rcs $@  $^

http.o: http.c $(IDIR)/http.h
	$(CC) $(CFLAGS) -I$(IDIR) -c http.c -o $@
	
net.o: net.c $(IDIR)/net.h
	$(CC) $(CFLAGS) -I$(IDIR) -c net.c -o $@
	
utils.o: utils.c $(IDIR)/utils.h
	$(CC) $(CFLAGS) -I$(IDIR) -c utils.c -o $@
	
clean:
	rm -f $(LIBDIR)/libcommon.a
	rm -f net.o http.o utils.o
