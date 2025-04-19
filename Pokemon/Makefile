CXX = g++
CXXFLAGS = -std=c++17 -Wall -Wextra -I./src

# Binary output location
TARGET_DIR = x64
TARGET = $(TARGET_DIR)/game.exe

# Source file structure
ROOT_SRC = main.cpp

SRC_DIRS = \
    src/Battle \
    src/Character \
    src/Character/Player \
    src/Main \
    src/Pokemon \
    src/Pokemon/Pokemons \
    src/Pokemon/StatusEffects \
    src/Utility

SRCS = $(ROOT_SRC) $(foreach dir, $(SRC_DIRS), $(wildcard $(dir)/*.cpp))
OBJS = $(SRCS:.cpp=.o)

# Build rules
all: $(TARGET)

$(TARGET): $(OBJS) | $(TARGET_DIR)
	$(CXX) $(CXXFLAGS) -o $@ $^

%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

$(TARGET_DIR):
	mkdir -p $(TARGET_DIR)

clean:
	rm -f $(OBJS) $(TARGET)

.PHONY: all clean
