
TARGET11  = $(BIN_DIR)/myprog11
TARGET18  =$(BIN_DIR)/myprog18
OBJ_DIR = ./obj
INC_DIR = .
BIN_DIR = ./bin
SRC_DIR = .
OBJS 	= $(OBJ_DIR)/hello.o
C11FLAGS= -std=c11 -Wall -I$(INC_DIR)
C18FLAGS= -std=c18 -Wall -I$(INC_DIR)

all: $(TARGET11) $(TARGET18)

$(TARGET11): $(OBJS)
	@mkdir -p $(BIN_DIR)
	gcc $(C11FLAGS) $(OBJS) -o $(TARGET11)

$(TARGET18): $(OBJS)
	@mkdir -p $(BIN_DIR)
	gcc $(C18FLAGS) $(OBJS) -o $(TARGET18)

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	mkdir -p $(OBJ_DIR)
	gcc -c $(C18FLAGS) $< -o $@

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	@mkdir -p $(OBJ_DIR)
	gcc -c $(C11FLAGS) $< -o $@

.PHONY: clean #.PHONY sirve para evitar confusion con otro archivo llamado clean
clean:
	@rm -f -r $(OBJ_DIR) $(BIN_DIR)
# -f es para ignorar instruccion en caso de no existir el archivo

.PHONY: run11
run11:
	@echo C11 >> output.txt
	@./$(TARGET11) >> output.txt
	@cat output.txt

.PHONY: run18
run18:
	@echo C18 >> output.txt
	@./$(TARGET18) >> output.txt
	@cat output.txt
