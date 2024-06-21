## The Heap as a memory concept

A free-floating [[Memory]] space, supports [[Dynamic Memory Allocation]] and by default most global variables are stored here. But it's not managed automatically mate so keep your eyes on this unless you want errors and overflow out the wazoo.

**Note**: It's also a *lot* slower to allocate and deallocate variables here compared to the [[Stack]].

Commonly represented by balanced [[Trees]] (BST) where the root node key is compared to its children and arranged accordingly.

Notes:
- Deallocation and memory management is crucial
- Hierarchical data structure
- Can be fragmented
- Allows access to variables globally

Min heap (Root is <= all children):
![[Pasted image 20220506102104.png]]

Max heap (Root is >= all children):
![[Pasted image 20220506102225.png]]

## The Heap and [[C++]]

Memory allocation on the heap in a C++ context occurs by way of the `new` and `delete` keywords primarily. `new` is really just a call to standard  `malloc` to allocate some contiguous chunk of memory to the data you have declared.

### Preallocation hacking

It is possible to preallocate a large chunk of memory and then go ahead with your heap allocation into that already reserved space which can sidestep the allocation inefficiency of the standard heap.

### [[C++ malloc]]


See also:
- [[C++]]
- [[Memory]]
- [Stack vs Heap Memory in C++](https://www.youtube.com/watch?v=wJ1L2nSIV1s)
