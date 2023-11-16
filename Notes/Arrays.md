A container which holds a fixed (normally) number of items of the same type.

Each element in the array has a position index.

Note that arrays are just [[Buffer]]s that have a determined (normally) size and type, in some languages this can be cast upwards or downwards.

E.g
1. You make a uint8 array of size 6
2. If you interpret it as a uint8 array, your computer treats the bytes as 8 byte chunks
3. If you cast it, you tell your computer to treat those same bytes as that type of chunk
4. So you need to be careful the values do not get read differently
#### Basic Operations
- Traversal
- Insertion (Overwrite really)
	- insertEnd (O(1))
	- insertMid (O(n))
- Deletion
	- removeEnd (O(1))
	- removeMid (O(n))
- Search
- Update


See also:
- [[Data Structures]]