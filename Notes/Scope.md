Scope, AKA 'access scope' AKA '[[Encapsulation]]', is the practice of setting the accessibility of methods, properties, classes, etc, etc.

The whole thing with this is *modesty baby*. We don't need everything hanging out in public for the world to see right? People don't need access to everything, unless that's your thing, but when it comes to code it shouldn't be your thing unless you like fucked code and malware.

### Public, private and protected, AKA don't touch the beer stash mate

Let's say you're a father, and because you have kids of course you drink alcohol, basically mandatory. You keep a stash of beers in the fridge and wanna control who can access them.

If we make those beers **_protected_**, then you're keeping them in the family so to speak, only subclasses (family members) can call the method (beers) and unrelated classes cannot, fuck 'em.

Let's say though, that you're feeling selfish and/or no one in your family is of legal drinking age. We'll channel our inner capitalist and **_private_** that method mate. Only you get access to it, a private method can only be called by the method that implements.

If you're feeling rich and generous though, well give everyone a beer mate, **_public_** that bad boy and watch them fly out the fucking door. Anything can access this method, object or whatever you're working with here.

## Non-degenerate Examples in [[C++]]

- **Global scope:** Identifiers declared outside any function or class have a global scope. They can be accessed from any part of the program (unless hidden by a local identifier with the same name). The lifetime of a global identifier is the entire duration of the program.

```cpp
#include <iostream>

int globalVar; // This is a global variable

int main() {
    std::cout << "Global variable: " << globalVar << std::endl;
}
```

- **Local scope:** Identifiers declared within [[Functions]] or a block have a local scope. They can be accessed only within the function or the block they were declared in. Their lifetime is limited to the duration of the function/block execution (See [[C++ Object Lifetime]]).

```cpp
#include <iostream>

void localExample() {
    int localVar; // This is a local variable
    localVar = 5;
    std::cout << "Local variable: " << localVar << std::endl;
}

int main() {
    localExample();
    // std::cout << localVar << std::endl; //error: ‘localVar’ was not declared in this scope
}
```

- **Namespace scope:** [[Namespaces]] are a named scope that groups related identifiers together. Identifiers declared within a namespace have the namespace scope. They can be accessed using the namespace name and the scope resolution operator `::`.

```cpp
#include <iostream>

namespace MyNamespace {
    int namespaceVar = 42;
}

int main() {
    std::cout << "Namespace variable: " << MyNamespace::namespaceVar << std::endl;
}
```

- **Class scope:** Identifiers declared within a class have a class scope. They can be accessed using the class name and the scope resolution operator `::` or, for non-static members, an object of the class and the dot `.` or arrow `->` operator.

```cpp
#include <iostream>

class MyClass {
public:
    static int staticMember;
    int nonStaticMember;

    MyClass(int value) : nonStaticMember(value) {}
};

int MyClass::staticMember = 7;

int main() {
    MyClass obj(10);
    std::cout << "Static member: " << MyClass::staticMember << std::endl;
    std::cout << "Non-static member: " << obj.nonStaticMember << std::endl;
}
```


See also:
- [[Computer Science Fundamentals]]

