C++ `malloc()` is a function used to allocate a requested number of bytes from [[Heap]] memory, returning a pointer to the first byte of allocated memory after being called, this memory is allocated at runtime, therefore malloc is a [[Dynamic Memory Allocation]] technique.

Returns a null [[Pointer]] if it fails.

## Note from cppreference on malloc [[Threads]] safety

> `malloc` is thread-safe: it behaves as though only accessing the memory locations visible through its argument, and not any static storage.
> 
> A previous call to [`free`](https://en.cppreference.com/w/c/memory/free "c/memory/free") or [`realloc`](https://en.cppreference.com/w/c/memory/realloc "c/memory/realloc") that deallocates a region of memory _synchronizes-with_ a call to `malloc` that allocates the same or a part of the same region of memory. This synchronization occurs after any access to the memory by the deallocating function and before any access to the memory by `malloc`. There is a single total order of all allocation and deallocation functions operating on each particular region of memory."


See also:
- [[C++]]
- [[Memory]]
- [A Memory Allocator - Doug Lea](https://gee.cs.oswego.edu/dl/html/malloc.html)
- [malloc - cppreference](https://en.cppreference.com/w/c/memory/malloc)