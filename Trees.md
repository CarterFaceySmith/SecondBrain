# Trees

A type of visual representation of data, nodes are connected by edges from a root node downwards normally.

The Binary Search Tree (BST) has the condition that each node can have a maximum of two children, hence the binary part of the name you moron. The left child node must have a val. less than the parent node and the right child node must have a val. greater than the parent node.

#### Basic Operations
- Insert
- Search
- Preorder traversal
- Inorder traversal
- Postorder traversal

#### Traversal
1. In-order traversal: left subtree visited first, then root, then right subtree, ie all the way left then up then right then  repeat.
2. Pre-order traversal: root visited first then left subtree, then right subtree.
3. Post-order traversal: root node visited last, left subtree visited first, then right, then root.

#### AVL Trees
An AVL tree is a tree that comes in a sorted manner already, giving it a weird branch like shape not akin to the regular BST, these trees need to be balanced out through reshaping due to poor efficiency in their base form.

AVL trees are usually balanced using a rotation technique, where we effectively rotate the position of a node in the tree to make it a new level and thereby moving the levels of the nodes connected to it to be lower (potentially making this node the new root) and balancing the tree.

![[Pasted image 20220506101900.png]]

#### Spanning Trees
A spanning tree is a subset of a graph which has all vertices covered with the min. possible number of edges, meaning the tree has no cycles and cannot be disconnected.

![[Pasted image 20220506102013.png]]


See also:
- [[Data Structures]]
- [[Algorithms]]