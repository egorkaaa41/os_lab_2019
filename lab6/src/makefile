CC=gcc
CFLAGS=-I.
all : client server

modulo.o: modulo.h
	$(CC) -o modulo.o -c modulo.c -std=c99 $(CFLAGS)
	
client : modulo.o modulo.h
	$(CC) -o client modulo.o client.c -lpthread -std=c99 $(CFLAGS)
	
server: modulo.o modulo.h
	$(CC) -o server modulo.o server.c -lpthread -std=c99 $(CFLAGS)
	
clean:
	rm -f client server modulo.o