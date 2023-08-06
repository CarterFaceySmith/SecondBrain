# Makefiles

A simple way to organise code compilation, especially in [[C++]].

Basically, instead of typing your whole compilation command ie gcc -o blah blah blah, we create a file that computes the latest changes and compiles them for you, whilst using a simpler syntax in the terminal to do so. Obviously this is called a makefile.

```c++
CC=gcc //the compiler flag, what we wanna use
CFLAGS=-I. //list of flags to pass to the compilation command

hellomake: hellomake.o hellofunc.o //tells the compiler hellomake needs to be executed if any of these files change
	$(CC) -o hellomake hellomake.o hellofunc.o // the command to run
```

Makefiles can be massively expanded with a number of rules and constraints to fit your scenario, you can read more on their potential online re flags, header files dependencies, macros, etc but here's a more advanced makefile for example.

```c++
IDIR =../include
CC=gcc
CFLAGS=-I$(IDIR)

ODIR=obj
LDIR =../lib

LIBS=-lm

_DEPS = hellomake.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = hellomake.o hellofunc.o 
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))


$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

hellomake: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~
```

See also:
- https://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/
- 