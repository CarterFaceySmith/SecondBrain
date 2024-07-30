Declaring a symbol before defining it in the code, helps the [[Compiler]] understand the type, size and existence of that symbol.

## Class Forward Declaration

To use a class type before it is defined, you can declare the class without defining its members, like this: `class ClassA; // forward declaration`

You can then use [[Pointer]]s or references to the class in your code before defining the class itself:

```cpp
void do_something (ClassA& obj);

class ClassB {
public:
    void another_function(ClassA& obj);
};
```

However, if you try to make an object of `ClassA` or call its member functions without defining the class, you will get a [[Compilation]] error.

## Function Forward Declaration

[[Functions]] must be declared before using them, and a forward declaration can be used to declare a function without defining it:

```cpp
int add(int a, int b); // forward declaration

int main() {
    int result = add(2, 3);
    return 0;
}

int add(int a, int b) {
    return a + b;
}
```

## Enum and Typedef Forward Declaration

For `enum` and `typedef`, it is not possible to forward declare because they don’t have separate declaration and definition stages.