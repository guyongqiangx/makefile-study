.PHONY: all

sources = foo.c bar.c baz.s ugh.h
sources := $(filter %.c %.s, $(sources))

all:
	@echo $(sources)
