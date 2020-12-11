.PHONY: clean

CC=gcc
RM=rm

EXE=simple.exe
OBJS=main.o foo.o

$(EXE):$(OBJS)
	$(CC) -o $@ $^

main.o: main.c
	$(CC) -o $@ -c $^

foo.o: foo.c
	$(CC) -o $@ -c $^

clean:
	$(RM) $(EXE) $(OBJS)
