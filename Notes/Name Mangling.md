The process of turning source program names into object file names.

AKA. *why the fuck some procedure names have a leading underscore*

Really it's just encoding them into a different name for use by the [[Compiler]] or [[Linkers]].

## Link-time Type Checking

>For linker type checking, each defined or undefined global symbol has associated with it a string representing the argument and return types, similar to the mangled C++ argument types. 
>
>When the linker resolves a symbol, *it compares the type strings for the reference and definition of the symbol, and reports an error if they don’t match*. A nice property of this scheme is that *the linker need not understand the type encoding at all, just whether the strings are the same or not*.

