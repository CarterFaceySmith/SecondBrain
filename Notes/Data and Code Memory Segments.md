## Data Segment

The Data segment is composed of two parts: the initialised data segment and the uninitialised data segment. The initialised data segment stores `global`, `static`, and `const` variables with initial values, whereas the uninitialised segment stores uninitialised `global` and `static` variables.

```cpp
// Initialized data segment
int globalVar = 10; // global variables
static int staticVar = 10; // static local variables
const int constVar = 10; // constant variables with value

// Uninitialized data segment
int globalVar; // uninitialized global variables
```

## Code Segment

The Code segment (also known as the Text segment) stores the executable code (machine code) of the program. It’s usually located in a read-only area of memory to prevent accidental modification.

```cpp
void functionExample() {
    // The machine code for this function is stored in the code segment.
}
```


See also:
- [[C++]]
- [[Memory]]