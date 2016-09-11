#compiler
CC=gcc
#compiler options
FLAGS=-Wall
# source directory
SRCDIR=src
# object directory
OBJDIR=out
#source files
SOURCES=$(wildcard $(SRCDIR)/*.c )
#object files
OBJECTS=$(patsubst $(SRCDIR)/%.c, $(OBJDIR)/%.o, $(SOURCES))

#executable filename
EXECUTABLE=main
#Special symbols used:
#$^ - is all the dependencies (in this case =$(OBJECTS) )
#$@ - is the result name (in this case =$(EXECUTABLE) )

all: $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS)
	$(CC) $^ -o $@

$(OBJDIR)/%.o: $(SRCDIR)/%.c
	$(CC) $(FLAGS) -c $^ -o $@

clean:
	rm $(EXECUTABLE) $(OBJECTS)

run: $(EXECUTABLE)
	./$(EXECUTABLE)

memcheck: $(EXECUTABLE)
	valgrind --tool=memcheck --leak-check=yes --show-reachable=yes --num-callers=20 --track-fds=yes ./$(EXECUTABLE)