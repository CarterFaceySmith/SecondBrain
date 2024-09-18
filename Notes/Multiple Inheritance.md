A feature of [[C++]] where [[C++ Classes]] can inherit characteristics (data members and functions) from more than one parent class.

The concept is similar to single [[Inheritance]], but here a class can have multiple base classes.

When a class inherits multiple base classes it becomes a mixture of their properties and behaviours and can override or extend them as needed.

## Syntax

```cpp
class DerivedClass : access-specifier BaseClass1, access-specifier BaseClass2, ...
{
    // class body
};
```

The `DerivedClass` will inherit members from both `BaseClass1` and `BaseClass2`. The `access-specifier` (like `public`, `protected`, or `private`) determines the accessibility of the inherited members.

Here is an example of multiple inheritance in action:

```cpp
#include <iostream>

// Base class 1
class Animal
{
public:
    void eat()
    {
        std::cout << "I can eat!" << std::endl;
    }
};

// Base class 2
class Mammal
{
public:
    void breath()
    {
        std::cout << "I can breathe!" << std::endl;
    }
};

// Derived class inheriting from both Animal and Mammal
class Dog : public Animal, public Mammal
{
public:
    void bark()
    {
        std::cout << "I can bark! Woof woof!" << std::endl;
    }
};

int main()
{
    Dog myDog;

    // Calling members from both base classes
    myDog.eat();
    myDog.breath();
    
    // Calling a member from the derived class
    myDog.bark();

    return 0;
}
```

## Diamond Inheritance

A specific scenario where a class is derived from two or more classes, which in turn are derived from a common base class. 

Creates ambiguity that arises from duplicating the common base class, leading to weird behaviour when calling duplicate members.

### How Do We Resolve Diamond Inheritance?

Uses virtual inheritance, a virtual base class is a class shared by multiple classes using the [[C++]] virtual keyword, ensuring only one copy of the base class is inherited in the final derived class.

```cpp
#include <iostream>

class Base {
public:
    void print() {
        std::cout << "Base class" << std::endl;
    }
};

class Derived1 : virtual public Base {
public:
    void derived1Print() {
        std::cout << "Derived1 class" << std::endl;
    }
};

class Derived2 : virtual public Base {
public:
    void derived2Print() {
        std::cout << "Derived2 class" << std::endl;
    }
};

class Derived3 : public Derived1, public Derived2 {
public:
    void derived3Print() {
        std::cout << "Derived3 class" << std::endl;
    }
};

int main() {
    Derived3 d3;
    d3.print(); // Now, there is no ambiguity in calling the base class function
    d3.derived1Print();
    d3.derived2Print();
    d3.derived3Print();

    return 0;
}
```

In the code above, `Derived1` and `Derived2` are derived from the `Base` class using virtual inheritance. So, when we create an object of `Derived3` and call the `print()` function from the `Base` class, there is no ambiguity, and the code executes without any issues.