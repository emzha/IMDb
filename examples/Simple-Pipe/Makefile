
CXX_FLAGS=-std=c++11 -Wall -fPIC
LD_FLAGS=-lila++

SRC_DIR=ila
OBJ_DIR=obj
SRC_FILES := $(wildcard $(SRC_DIR)/*.cc)
OBJ_FILES := $(patsubst $(SRC_DIR)/%.cc,$(OBJ_DIR)/%.o,$(SRC_FILES))

$(shell mkdir -p $(OBJ_DIR))

main: $(OBJ_FILES)
	   $(CXX) -o $@ $^ $(LD_FLAGS) 
	   mkdir -p vlg-gen

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.cc
	   $(CXX) $(CXX_FLAGS) -c -o $@ $<

all: main.exe

clean:
	rm -rf $(OBJ_DIR)/*
	rm -rf trace.vcd
	rm -rf YosysScript.ys
	rm -rf vlg-gen/*
