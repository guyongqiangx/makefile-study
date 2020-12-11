.PHONY: clean

CC=gcc
RM=rm

EXE=simple.exe
OBJS=main.o foo.o

$(EXE):$(OBJS)
	$(CC) -o $(EXE) $(OBJS)

main.o: main.c
	$(CC) -o main.o -c main.c

foo.o: foo.c
	$(CC) -o foo.o -c foo.c

clean:
	$(RM) $(EXE) $(OBJS) 
