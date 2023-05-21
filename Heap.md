# Heap

A free-floating memory space, supports [[Dynamic Memory Allocation]] and by default most global variables are stored here. But it's not managed automatically mate so keep your eyes on this unless you want errors and overflow out the wazoo.

Commonly represented by a balanced [[Trees]] (BST) where the root node key is compared to its children and arranged accordingly.

Notes:
- deallocation and memory management is crucial
- hierarchical data structure
- can be fragmented
- allows access to variables globally

Min heap (Root is <= all children):
![[Pasted image 20220506102104.png]]

Max heap (Root is >= all children):
![[Pasted image 20220506102225.png]]

See also:
- [[C++]]
- [[Memory]]
