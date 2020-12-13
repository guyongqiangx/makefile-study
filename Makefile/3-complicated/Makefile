.PHONY: all clean

MKDIR = mkdir
RM = rm
RMFLAGS = -fr

cc = gcc

DIR_OBJS = objs
DIR_EXES = exes
DIR_DEPS = deps
DIRS = $(DIR_OBJS) $(DIR_EXES) $(DIR_DEPS)
EXE = complicated.exe
EXE := $(addprefix $(DIR_EXES)/, $(EXE))
SRCS = $(wildcard *.c)
OBJS = $(SRCS:.c=.o)
OBJS := $(addprefix $(DIR_OBJS)/, $(OBJS))
DEPS = $(SRCS:.c=.dep)
DEPS := $(addprefix $(DIR_DEPS)/, $(DEPS))

all: $(DIRS) $(DEPS) $(EXE)

include $(DEPS)

$(DIRS):
	$(MKDIR) $@

$(EXE): $(OBJS)
	$(CC) -o $@ $^

$(DIR_OBJS)/%.o: %.c
	$(CC) -o $@ -c $^

$(DIR_DEPS)/%.dep: %.c
	@echo "Making $@..."
	@set -e; \
	$(RM) $(RMFLAGS) $@.tmp; \
	$(CC) -E -MM $^ > $@.tmp; \
	sed 's,\(.*\)\.o[ :]*,objs/\1.o: ,g' < $@.tmp > $@; \
	$(RM) $(RMFLAGS) $@.tmp

clean:
	$(RM) $(RMFLAGS) $(DIRS)
