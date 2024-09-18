What is a library? A pre-compiled piece of code that can be reused in your program to perform a specific task or provide certain functionality, in [[C++]] these can be static (`.lib`) or dynamic (`.dll` in Windows, `.so` in Unix/[[Linux]]).

## Static Libraries

Static libraries are incorporated into your program during [[Compilation]] time. They are linked with your code (See [[Linkers]]), creating a larger executable file, but it does not require any external files during runtime.

To create a static library, you’ll need to compile your source files into object files, then bundle them into an archive. You can use the following commands:

```
g++ -c sourcefile.cpp -o objectfile.o
ar rcs libmystaticlibrary.a objectfile.o
```

To use a static library, you need to include the header files in your source code and then link the library during the [[Compilation]] process:

```
g++ main.cpp -o myprogram -L/path/to/your/library/ -lmystaticlibrary
```

Replace `/path/to/your/library/` with the path where your `libmystaticlibrary.a` file is located.

## Dynamic Libraries

Dynamic libraries are loaded during runtime, which means that your executable file only contains references to these libraries. The libraries need to be available on the system where your program is running.

To create a dynamic library, you’ll need to compile your source files into [[Object Files]], then create a shared library:

```
g++ -c -fPIC sourcefile.cpp -o objectfile.o
g++ -shared -o libmydynamiclibrary.so objectfile.o
```

To use a dynamic library, include the library’s header files in your source code and then link the library during the compilation process:

```
g++ main.cpp -o myprogram -L/path/to/your/library/ -lmydynamiclibrary
```

Replace `/path/to/your/library/` with the path where your `libmydynamiclibrary.so` file is located.

**NOTE:** When using dynamic libraries, make sure the library is in the system’s search path for shared libraries. You may need to update the `LD_LIBRARY_PATH` environment variable on Unix/Linux systems or the `PATH` variable on Windows.