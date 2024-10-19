We can avoid the duplicate header definition problem via a mechanism called a **header guard** (also called an **include guard**). Header guards are conditional compilation directives that take the following form:

```cpp
#ifndef SOME_UNIQUE_NAME_HERE
#define SOME_UNIQUE_NAME_HERE

// your declarations (and certain types of definitions) here

#endif
```

When this header is \#included, the preprocessor will check whether _SOME_UNIQUE_NAME_HERE_ has been previously defined in this translation unit. If this is the first time we’re including the header, _SOME_UNIQUE_NAME_HERE_ will not have been defined. Consequently, it \#defines _SOME_UNIQUE_NAME_HERE_ and includes the contents of the file. 

If the header is included again into the same file, _SOME_UNIQUE_NAME_HERE_ will already have been defined from the first time the contents of the header were included, and the contents of the header will be ignored (thanks to the \#ifndef).

All of your [[C++ Header Files]] should have header guards on them. 

_SOME_UNIQUE_NAME_HERE_ can be any name you want, but by convention is set to the full filename of the header file, typed in all caps, using underscores for spaces or punctuation. 

***Tossing a minor fuck around into the mix***

In large programs, it’s possible to have two separate header files (included from different directories) that end up having the same filename (e.g. directoryA\config.h and directoryB\config.h). 

If only the filename is used for the include guard (e.g. CONFIG_H), these two files may end up using the same guard name. If that happens, any file that includes (directly or indirectly) both config.h files will not receive the contents of the include file to be included second. This will probably cause a compilation error.

Because of this possibility for guard name conflicts, many developers recommend using a more complex/unique name in your header guards. Some good suggestions are a naming convention of PROJECT_PATH_FILE_H, FILE_LARGE-RANDOM-NUMBER_H, or FILE_CREATION-DATE_H.

## Why Can't I Just Not Define in Header Files? That's Standard Practice Anyway!

There are quite a few cases we’ll show you in the future where it’s necessary to put non-function definitions in a header file. 

For example, [[C++]] will let you create your own types. These custom types are typically defined in header files, so the type definitions can be propagated out to the code files that need to use them. Without a header guard, a code file could end up with multiple (identical) copies of a given type definition, which the compiler will flag as an error.

## [[Pragma Preprocessor Directive]]