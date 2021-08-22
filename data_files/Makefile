CC=gcc
CFLAGS=-O3
LDFLAGS=-lc -lm -lSDL
EXEC=bmptoh

all: $(EXEC)

bmptoh: pack.o lzw.o bmptoh.o
	$(CC) -o $@    $^ $(LDFLAGS)

bmptoh.o: bmptoh.c
	$(CC) -o $@ -c $< $(CFLAGS)

pack.o: ../packer/pack.c ../packer/pack.h
	$(CC) -o $@ -c $< $(CFLAGS)

lzw.o: ../packer/lzw.c ../packer/lzw.h
	$(CC) -o $@ -c $< $(CFLAGS)

clean:
	rm -rf *.o

mrproper: clean
	rm -rf $(EXEC)

.PHONY: clean mrproper
