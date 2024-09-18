`dynamic_cast` is a type of [[Typecasting]] operator in [[C++]] that is used specifically for polymorphism. It safely converts pointers and references of a base [[C++ Classes]] to its derived class and checks the validity of the conversion during runtime. 

If the conversion is not valid (i.e., the object is not of the target type), it returns a null [[Pointer]] instead of producing undefined behaviour. Therefore, `dynamic_cast` can prevent potential crashes and errors when using [[Polymorphism]].

```cpp
#include <iostream>

class BaseClass {
   public:
    virtual void display() {
        std::cout << "BaseClass" << std::endl;
    }
};

class DerivedClass : public BaseClass {
   public:
    void display() {
        std::cout << "DerivedClass" << std::endl;
    }
};

int main() {
    BaseClass *basePtr = new DerivedClass();  // Upcasting
    DerivedClass *derivedPtr;

    derivedPtr = dynamic_cast<DerivedClass *>(basePtr);  // Downcasting
    if (derivedPtr) {
        derivedPtr->display();  // Output: DerivedClass
    } else {
        std::cout << "Invalid type conversion.";
    }

    delete basePtr;
    return 0;
}
```

In this example, a pointer to a `DerivedClass` object is assigned to a `BaseClass` pointer (`basePtr`). Then, we attempt to downcast it back to a `DerivedClass` pointer using `dynamic_cast`. If the casting is successful, we can access the `DerivedClass` functionality through the new pointer (`derivedPtr`).

## How does the compiler know that the class is what it is?

C++ stores stores runtime type information (RTTI) about all of our types, this is what allows this functionality, but adds overhead.


See also:
- [[C++]]
- [Dynamic Casting in C++ - TheCherno](https://www.youtube.com/watch?v=CiHfz6pTolQ&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb&index=73)