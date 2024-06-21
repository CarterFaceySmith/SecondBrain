When dealing with [[Qt QML]] items, the $x$ and $y$ properties are relative to the parent of whatever that child is. 

Another thing of note is $y$ goes down, not up.

Therefore origin $(0,0)$ is the upper-left corner of the item.

There is a `mapToGlobal` function if you need to get the global placement based on a local $x$ and $y$.

## Anchors

Allows the programmer to define an anchor point for some item relative to some other item as long as it is a parent or sibling of the item being anchored.

## Positioner Items (A.K.A Containers)
- Row
- Column
- Flow
- Grid

Self explanatory really, use them to predefine a container area for a number of elements.
## Layouts
Layouts auto-adjust and resize the position of encompassed children based on their preferred size and space.

What's the difference between this and positioners? Layouts are more flexible and responsive, they allow for more granular control over the relativity of your items.