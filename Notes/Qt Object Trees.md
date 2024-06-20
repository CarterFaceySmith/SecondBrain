Each [[Qt QML]] object can have one parent which gets set by the constructor, each child can then of course become a parent to their own children. This defines the basic concept behind Qt object trees.

This is useful because when a destructor is called, it will iterate over the object tree and destroy all children of the object as well.

**Note**: Qt objects have their copy constructor removed by default because of this, if you could copy it you might end up copying a massive quantity of children too and there children etc.

## Practical Example of Qt Object Trees

Let's say you have some main window which can open sub windows based on tasks, if you close the main window you likely want the sub windows to close too right?

