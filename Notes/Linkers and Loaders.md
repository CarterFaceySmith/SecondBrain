> The basic job of any linker or loader is simple: it binds more abstract names to more concrete names, which permits programmers to write code using the more abstract names. That is, it takes a name written by a programmer such as `getline` and binds it to ‘‘*the location 612 bytes from the beginning of the executable code in module `iosys`.*’’ 
> 
> Or it may take a more abstract numeric address such as ‘‘*the location 450 bytes beyond the beginning of the static data for this module*’’ and bind it to a numeric address.
> 
> John R. Levine in his book, '*Linkers & Loaders*'

## Key Tasks

- Program loading: Copying a program from secondary storage to main memory so it's ready to run.
- [[Relocation]]: Assigning load addresses to the parts of the program, adjusting the code and data in it to reflect the available addresses assigned by the computer (to avoid overlapping addresses).
- Symbol resolution: Resolving symbol references, i.e. if you call a routine from a library the linker notes the location assigned to that routine in the library and patches the caller's object code to it so it refers to that location.

### A Note on Overlapping Responsibilities

Programs can be linkers (symbol resolution), loaders (program loading) or both. Any of those options can do relocation.

All options patch object code, one of the few programs outside of debuggers that does this, very powerful and very easy to fuck up.

## [[Linkers]]



See also:
- [[Compilation in C++]]
- *Linkers & Loaders* by John R. Levine