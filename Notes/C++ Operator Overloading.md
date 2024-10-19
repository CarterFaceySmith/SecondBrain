>"In [[C++]], operators are implemented as [[Functions]]. By using [[Function Overloading]] on the operator functions, you can define your own versions of the operators that work with different data types (including [[C++ Classes]] that you’ve written). Using function overloading to overload operators is called **operator overloading**." - Learncpp

E.g. `std::cout << x + y << std::endl;`

However, what about this?

```cpp
Mystring string1 { "Hello, " };
Mystring string2 { "World!" };
std::cout << string1 + string2 << '\n';
```

What would you expect to happen in this case? 

Because Mystring is a program-defined type, the [[Compiler]] does not have a built-in version of the plus operator that it can use for Mystring operands. So in this case, it will give us an error. 

In order to make it work like we want, we’d need to write an overloaded function to tell the compiler how the + operator should work with two operands of type Mystring. 

## The Resolution Process for Overloaded Operators

1. If all operands are fundamental datatypes, compiler calls a built-in routine, or produces a compiler error if no routine exists
2. If any of the operands are not fundamental, the compiler will try to find an overloaded operator that is a best match, it may implicitly convert one or more operands to match the parameter type of the overloaded operator too
	1. Can also implicit convert program-defined types into fundamental types to match a built-in operator
	2. Produces a compiler error if no match found

## Limitations

- Almost any existing operator in C++ can be overloaded. The exceptions are: conditional (?:), sizeof, scope (::), member selector (.), pointer member selector (.\*), typeid, and the casting operators
- You can only overload the operators that exist. You can not create new operators or rename existing operators
	- For example, you could not create an `operator**` to do exponents.
- At least one of the operands in an overloaded operator must be a user-defined type
	- E.g. you could overload `operator+(int, Mystring)`, but not `operator+(int, double)`
- It is not possible to change the number of operands an operator supports
- All operators keep their default precedence and associativity (regardless of what they’re used for) and this can not be changed

### Standards and Best Practices

- Best practice is that your overloaded operators should operate on at least one program-defined type. This guarantees that a future language standard won’t potentially break your programs by defining this overload.

- If the meaning of an overloaded operator is not clear and intuitive, use a named function instead.

- Operators that do not modify their operands (e.g. arithmetic operators) should generally return results using [[Pass-by-value]]

- Operators that modify their leftmost operand (e.g. pre-increment, any of the assignment operators) should generally return the leftmost operand using [[Pass-by-reference]].

## [[C++ Arithmetic Operator Overloading]]