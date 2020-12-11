.PHONY: all

cc = gcc
RM = rm

EXE = simple.exe
SRCS = $(wildcard *.c)
OBJS = $(patsubst %.c,%.o,$(SRCS))

all: $(EXE)

$(EXE): $(OBJS)
	$(CC) -o $@ $^

%.o: %.c
	$(CC) -o $@ -c $^

clean:
	$(RM) $(EXE) $(OBJS)
