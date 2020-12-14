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

all: $(EXE)

ifneq ($(MAKECMDGOALS),clean)
-include $(DEPS)
endif

$(DIRS):
	$(MKDIR) $@

$(EXE): $(OBJS)
	@set -e; \
	if [ ! -e $(DIR_EXES) ]; then \
		$(MKDIR) $(DIR_EXES); \
	fi;
	$(CC) -o $@ $(filter %.o, $^)

$(DIR_OBJS)/%.o: %.c
	@set -e; \
	if [ ! -e $(DIR_OBJS) ]; then \
		$(MKDIR) $(DIR_OBJS); \
	fi;
	$(CC) -o $@ -c $(filter %.c, $^)

$(DIR_DEPS)/%.dep: %.c
	@echo "Making $@..."
	@set -e; \
	if [ ! -e $(DIR_DEPS) ]; then \
		$(MKDIR) $(DIR_DEPS); \
	fi; \
	$(RM) $(RMFLAGS) $@.tmp; \
	$(CC) -E -MM $(filter %.c, $^) > $@.tmp; \
	sed 's,\(.*\)\.o[ :]*,objs/\1.o $@: ,g' < $@.tmp > $@; \
	$(RM) $(RMFLAGS) $@.tmp

clean:
	$(RM) $(RMFLAGS) $(DIRS)
