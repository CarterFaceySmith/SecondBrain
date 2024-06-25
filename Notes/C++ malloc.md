C++ `malloc()` is a function used to allocate a requested number of bytes from [[Heap]] memory, returning a pointer to the first byte of allocated memory after being called, this memory is allocated at runtime, therefore malloc is a [[Dynamic Memory Allocation]] technique.

Returns a null [[Pointer]] if it fails.

## Note from cppreference on `malloc` [[Threads]] safety

> `malloc` is thread-safe: it behaves as though only accessing the memory locations visible through its argument, and not any static storage.
> 
> A previous call to [`free`](https://en.cppreference.com/w/c/memory/free "c/memory/free") or [`realloc`](https://en.cppreference.com/w/c/memory/realloc "c/memory/realloc") that deallocates a region of memory _synchronizes-with_ a call to `malloc` that allocates the same or a part of the same region of memory. This synchronization occurs after any access to the memory by the deallocating function and before any access to the memory by `malloc`. There is a single total order of all allocation and deallocation functions operating on each particular region of memory."

## The `malloc` algorithm

### Boundary tags

Chunks of [[Memory]] have size information before and after the chunk, allowing two bordering unused chunks to be coalesced into one larger chunk, and all chunks can be traversed starting from any known chunk forwards or backwards.

![[Pasted image 20240624144305.png]]

### Binning

Available chunks are maintained in size ordered bins. Searches for available chunks are processed in smallest first, best-fit order in order to lessen the chance of [[Fragmentation]].

![[Pasted image 20240624144451.png]]



See also:
- [[C++]]
- [[Memory]]
- [A Memory Allocator - Doug Lea](https://gee.cs.oswego.edu/dl/html/malloc.html)
- [malloc - cppreference](https://en.cppreference.com/w/c/memory/malloc)