.PHONY: all

cc = gcc
RM = rm

EXE = simple.exe
OBJS = main.o foo.o

all: $(EXE)

$(EXE): $(OBJS)
	$(CC) -o $@ $^

%.o: %.c
	$(CC) -o $@ -c $^

clean:
	$(RM) $(EXE) $(OBJS)
