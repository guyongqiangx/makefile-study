.PHONY: all

mixed = foo.c bar.c main.o
objects := $(patsubst %.c, %.o, $(mixed))

all:
	@echo $(objects)
