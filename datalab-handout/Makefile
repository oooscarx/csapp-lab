#
# Makefile that builds btest and other helper programs for the CS:APP data lab
# 
CC = gcc
# Some targets don't have 32-bit glibc headers installed. Enable -m32 only
# when explicitly requested: `make M32=1`.
CFLAGS = -O -Wall
M32 ?= 0
ifeq ($(M32),1)
CFLAGS += -m32
endif
LIBS = -lm

all: btest fshow ishow

btest: btest.c bits.c decl.c tests.c btest.h bits.h
	$(CC) $(CFLAGS) $(LIBS) -o btest bits.c btest.c decl.c tests.c

fshow: fshow.c
	$(CC) $(CFLAGS) -o fshow fshow.c

ishow: ishow.c
	$(CC) $(CFLAGS) -o ishow ishow.c

# Forces a recompile. Used by the driver program. 
btestexplicit:
	$(CC) $(CFLAGS) $(LIBS) -o btest bits.c btest.c decl.c tests.c 

clean:
	rm -f *.o btest fshow ishow *~

