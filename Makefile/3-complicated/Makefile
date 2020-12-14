.PHONY: all

sharp = square
desk = square
table = circle

ifeq ($(sharp), $(desk))
result1 = "desk == sharp"
endif

ifneq "$(table)" 'square'
result2 = "table != square"
endif

all:
	@echo $(result1)
	@echo $(result2)
