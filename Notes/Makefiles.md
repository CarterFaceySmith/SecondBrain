A simple way to organise code compilation, especially in [[C++]].

It is a type of [[Build Systems]].

Basically, instead of typing your whole compilation command ie gcc -o blah blah blah, we create a file that computes the latest changes and compiles them for you, whilst using a simpler syntax in the terminal to do so. Obviously this is called a makefile.

The pretty groovy thing is it only recompiles changes, so unchanged files don't get recompiled (unless you've run a clean of course).

```c++
CC=gcc //the compiler flag, what we wanna use
CFLAGS=-I. //list of flags to pass to the compilation command

hellomake: hellomake.o hellofunc.o //tells the compiler hellomake needs to be executed if any of these files change
	$(CC) -o hellomake hellomake.o hellofunc.o // the command to run
```

Makefiles can be massively expanded with a number of rules and constraints to fit your scenario, you can read more on their potential online re flags, header files dependencies, macros, etc but here's a more advanced makefile for example.

Then you can get into nested Makefiles with higher level Makefiles calling the lower level ones right? So you have some tool with a .c and .h file, a higher level .c file relies on that so you say ok make that first then this second.

```c++
IDIR =../include
CC=gcc // The compiler
CFLAGS=-I$(IDIR) // Include the files in the IDIR defined above

ODIR=obj // Obj dir from file location
LDIR =../lib // Declaration of lib dir relative to file location

LIBS=-lm // Any libraries your code relies on go here as l<name>, so here there is literally some library just called m (i.e. libm.h)

_DEPS = hellomake.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = hellomake.o hellofunc.o // What to compile to
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))
// patsubst is string pattern substitution, i.e. take anything that matches x and turn it into y, here anything in the ODIR gets turned into _OBJ

$(ODIR)/%.o: %.c $(DEPS) // generation of all .o into ODIR depends on generation of all .c and all deps
	$(CC) -c -o $@ $< $(CFLAGS)

hellomake: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~
```

Notes:
- That @ symbol means whatever is to the left of the colon, i.e. the target
- The carrot ^ means whatever is on the right hand side of the colon, i.e. the dependency
- $< evaluates to the first prerequisite file (normally the source file)

## More Notes

- Makefiles have loops, you can loop through directories for include files or some such and do something, e.g. generate the compiled include


See also:
- https://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/
- 