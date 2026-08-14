include makefile.linux

CCFLAGS = $(MODE) -c -Wall -pedantic -ansi
SRC_DIR = .
BIN_DIR= ../bin
OBJ_DIR = $(BIN_DIR)/obj

FIXTURES = $(BIN_DIR)/fixtures
ROSTER_CREATOR = $(BIN_DIR)/roster_creator
TSC = $(BIN_DIR)/tsc
ESMS = $(BIN_DIR)/esms
UPDTR = $(BIN_DIR)/updtr
LGTABLE = $(BIN_DIR)/lgtable

ESMS_O_FILES = \
	$(OBJ_DIR)/rosterplayer.o \
	$(OBJ_DIR)/comment.o \
	$(OBJ_DIR)/penalty.o \
	$(OBJ_DIR)/report_event.o \
	$(OBJ_DIR)/esms.o \
	$(OBJ_DIR)/cond_utils.o \
	$(OBJ_DIR)/teamsheet_reader.o \
	$(OBJ_DIR)/cond_action.o \
	$(OBJ_DIR)/cond_condition.o \
	$(OBJ_DIR)/util.o \
	$(OBJ_DIR)/cond.o \
	$(OBJ_DIR)/mt.o \
	$(OBJ_DIR)/config.o \
	$(OBJ_DIR)/tactics.o \
	$(OBJ_DIR)/anyoption.o

UPDTR_O_FILES = \
	$(OBJ_DIR)/rosterplayer.o \
	$(OBJ_DIR)/updtr.o \
	$(OBJ_DIR)/util.o \
	$(OBJ_DIR)/anyoption.o \
	$(OBJ_DIR)/config.o \
	$(OBJ_DIR)/comment.o \
	$(OBJ_DIR)/league_table.o

LGTABLE_O_FILES = \
	$(OBJ_DIR)/lgtable.o \
	$(OBJ_DIR)/league_table.o \
	$(OBJ_DIR)/util.o \
	$(OBJ_DIR)/anyoption.o

FIXTURES_O_FILES = \
	$(OBJ_DIR)/fixtures.o \
	$(OBJ_DIR)/util.o \
	$(OBJ_DIR)/anyoption.o

TSC_O_FILES = \
	$(OBJ_DIR)/tsc.o \
	$(OBJ_DIR)/rosterplayer.o \
	$(OBJ_DIR)/util.o \
	$(OBJ_DIR)/config.o

ROSTER_CREATOR_O_FILES = \
	$(OBJ_DIR)/roster_creator.o \
	$(OBJ_DIR)/rosterplayer.o \
	$(OBJ_DIR)/anyoption.o \
	$(OBJ_DIR)/config.o \
	$(OBJ_DIR)/util.o

.PHONY: all clean

all: $(ESMS) $(ROSTER_CREATOR) $(LGTABLE) $(UPDTR) $(FIXTURES) $(TSC)

$(TSC): $(TSC_O_FILES) | $(BIN_DIR)
	$(CC) -o $@ $^

$(ROSTER_CREATOR): $(ROSTER_CREATOR_O_FILES) | $(BIN_DIR)
	$(CC) -o $@ $^

$(LGTABLE): $(LGTABLE_O_FILES) | $(BIN_DIR)
	$(CC) -o $@ $^

$(UPDTR): $(UPDTR_O_FILES)  | $(BIN_DIR)
	$(CC) -o $@ $^

$(ESMS): $(ESMS_O_FILES) | $(BIN_DIR)
	$(CC) -o $@ $^

$(FIXTURES): $(FIXTURES_O_FILES) | $(BIN_DIR)
	$(CC) -o $@ $^

$(OBJ_DIR)/%.o : $(SRC_DIR)/%.cpp | $(OBJ_DIR)
	$(CC) $(CCFLAGS) -c $< -o $@

$(BIN_DIR) $(OBJ_DIR):
	mkdir -p $@

clean: 
	\rm -rf $(BIN_DIR)

