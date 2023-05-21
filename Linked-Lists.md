# Linked-Lists

A sequence of data structures linked together via links in some way.

Each link carries a data field and a link field to next, this can depend on the type of linked-list though, see below.

#### Simply Linked-Lists
Item navigation is forward only.

#### Basic Operations
- Insertion: Add elem to beginning of list
- Deletion: Delete elem from beginning of list
- Display of complete list
- Search: Searches an elem using a given key
- Delete: Deletes an elem using the given key

#### Doubly Linked-Lists
A linked list with pointers for the chain of nodes in *both* directions, each node points to a prev. and next unless they're the end/start node.

Has a link field to prev and to next, last and first data fields link their requisite link fields on one side to null.

#### Basic Operations
- Insertion: Add elem to beginning of list
- Deletion: Delete elem from beginning of list
- Insert last
- Delete last
- Insert after
- Delete
- Display forward
- Display backward

#### Circularly Linked-Lists
Last item contains a link to the head item as next, and head item has a link to last item as previous.

#### Basic Operations
- Insert
- Delete
- Display


See also:
- [[Algorithms]]
- [[Asymptotic Complexity]]
- [[Data Structures]]