CFLAGS = -O3 -I../.. -Wall
LDFLAGS =

EXEC=bmptoh

all: $(EXEC)

bmptoh: bmptoh.o lzw.o pack.o rle.o
	$(CC) -o $@    $^ $(LDFLAGS)

bmptoh.o: bmptoh.c
	$(CC) -o $@ -c $< $(CFLAGS)

lzw.o: ../mi_pack/lzw.c
	$(CC) -o $@ -c $< $(CFLAGS)

pack.o: ../mi_pack/pack.c
	$(CC) -o $@ -c $< $(CFLAGS)

rle.o: ../mi_pack/rle.c
	$(CC) -o $@ -c $< $(CFLAGS)

clean:
	rm -rf *.o

mrproper: clean
	rm -rf $(EXEC)
	rm -rf Debug*
	rm -rf Release*
	rm -rf *.obj *.ncb *.plg *.opt

.PHONY: clean mrproper
