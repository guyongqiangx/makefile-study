.PHONY: all

without_dir = foo.c bar.c main.o
with_dir := $(addprefix objs/,$(without_dir))

all:
	@echo $(with_dir)
