CC=gcc
CFLAGS=-I.

all : parallel_min_max zombie_making process_memory parallel_sum

parallel_min_max : utils.o find_min_max.o utils.h find_min_max.h
	$(CC) -o parallel_min_max utils.o find_min_max.o parallel_min_max.c -std=c99 $(CFLAGS)

zombie_making: zombie_making.c
	@$(CC) -o zombie_making zombie_making.c -std=c99 $(CFLAGS)
	@chmod u+rwx ./zombie_making

process_memory : process_memory.c
	@$(CC) process_memory.c -o process_memory -std=c99 $(CFLAGS)

parallel_sum: parallel_sum.c sum.o utils.o
	@$(CC) -o parallel_sum utils.o sum.o parallel_sum.c -lpthread -std=c99 $(CFLAGS)

find_min_max.o : utils.o find_min_max.h find_min_max.c
	@$(CC) -o find_min_max.o -c find_min_max.c  -std=c99 $(CFLAGS)

utils.o : utils.h utils.c
	@$(CC) -o utils.o -c utils.c  -std=c99 $(CFLAGS)

sum.o : sum.h sum.c
	$(CC) -o sum.o -c sum.c  -std=c99 $(CFLAGS)

clean :
	rm utils.o find_min_max.o parallel_min_max zombie_making process_memory
