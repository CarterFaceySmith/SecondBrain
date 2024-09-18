AKA Vtables.

A mechanism used by [[C++]] to support dynamic [[Polymorphism]] (calling the right function at runtime depending on the actual object type).

If a [[C++ Classes]] contains a [[C++ Virtual Function]] the [[Compiler]] will create the vtable for that class, which contains function [[Pointer]]s to the virtual functions defined in the class.

Each object of that class has a pointer to its vtable (vptr) automatically initialised by the compiler during object construction.

Let’s consider the following example:

```cpp
class Base {
public:
    virtual void function1() {
        std::cout << "Base::function1" << std::endl;
    }

    virtual void function2() {
        std::cout << "Base::function2" << std::endl;
    }
};

class Derived : public Base {
public:
    void function1() override {
        std::cout << "Derived::function1" << std::endl;
    }

    void function3() {
        std::cout << "Derived::function3" << std::endl;
    }
};

int main() {
    Base* obj = new Derived(); // create a Derived object and assign a pointer of type Base*
    obj->function1(); // calls Derived::function1, due to dynamic polymorphism
    obj->function2(); // calls Base::function2

    delete obj;
    return 0;
}
```

In this example, when a `Derived` object is created, the compiler generates a Vtable for `Derived` class, containing pointers to its virtual functions:

- `Derived::function1` (overridden from `Base`)
- `Base::function2` (inherits from Base)

The `_vptr_` pointer in the `Derived` object points to this Vtable. When the `function1` is called on the `Base` pointer pointing to the `Derived` object, the function pointer in the Vtable is used to call the correct function (in this case, `Derived::function1`). Similarly, the call to `function2` calls `Base::function2`, since it’s the function pointer stored in the Vtable for `Derived` class.