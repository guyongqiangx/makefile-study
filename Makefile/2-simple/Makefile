.PHONY: all

objects = main1.o foo.o main2.o bar.o
result = $(filter-out main%.o, $(objects))

all:
	@echo $(result)
