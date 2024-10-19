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

## [[C++ Operator Overloading Using Member Functions]]

## The Catch, i.e. Which Should I Use?

So if we can overload an operator as a friend or a member, which should we use? In order to answer that question, there’s a few more things you’ll need to know.

**Not everything can be overloaded as a friend function**

The assignment (=), subscript ([]), function call (()), and member selection (->) operators must be overloaded as member functions, because the language requires them to be.

**Not everything can be overloaded as a member function**

We are not able to overload operator<< as a member function. Why not? Because the overloaded operator must be added as a member of the left operand. In this case, the left operand is an object of type std::ostream. std::ostream is fixed as part of the standard library. We can’t modify the class declaration to add the overload as a member function of std::ostream.

***So when do I use a normal, friend or member function overload???***

The following rules of thumb can help you determine which form is best for a given situation:

- If you’re overloading assignment (=), subscript ([]), function call (()), or member selection (->), do so as a member function.
- If you’re overloading a unary operator, do so as a member function.
- If you’re overloading a binary operator that does not modify its left operand (e.g. operator+), do so as a normal function (preferred) or friend function.
- If you’re overloading a binary operator that modifies its left operand, but you can’t add members to the class definition of the left operand (e.g. operator<<, which has a left operand of type ostream), do so as a normal function (preferred) or friend function.
- If you’re overloading a binary operator that modifies its left operand (e.g. operator+=), and you can modify the definition of the left operand, do so as a member function.

## The Absolute Summary and Areas Not Covered (Yet)

Operators can be overloaded as a normal function, a friend function, or a member function. The following rules of thumb can help you determine which form is best for a given situation:

- If you’re overloading assignment (=), subscript ([]), function call (()), or member selection (->), do so as a member function.
- If you’re overloading a unary operator, do so as a member function.
- If you’re overloading a binary operator that modifies its left operand (e.g. operator+=), do so as a member function if you can.
- If you’re overloading a binary operator that does not modify its left operand (e.g. operator+), do so as a normal function or friend function.

[[Typecasting]] can be overloaded to provide conversion functions, which can be used to explicitly or implicitly convert your class into another type.

A copy constructor is a special type of constructor used to initialise an object from another object of the same type. Copy constructors are used for direct/uniform initialisation from an object of the same type, copy initialisation (Fraction f = Fraction(5,3)), and when passing or returning a parameter by value.

If you do not supply a copy constructor, the [[Compiler]] will create one for you. Compiler-provided copy constructors will use memberwise initialisation, meaning each member of the copy is initialised from the original member. The copy constructor may be elided (omitted) for optimisation purposes, even if it has side-effects, so do not rely on your copy constructor actually executing.

Constructors are considered converting constructors by default, meaning that the compiler will use them to implicitly convert objects of other types into objects of your class. You can avoid this by using the explicit keyword in front of your constructor. You can also delete functions within your class, including the copy constructor and overloaded assignment operator if desired. This will cause a compiler error if a deleted function would be called.

The assignment operator can be overloaded to allow assignment to your class. If you do not provide an overloaded assignment operator, the compiler will create one for you. Overloaded assignment operators should always include a self-assignment check (unless it’s handled naturally, or you’re using the copy and swap idiom).

New programmers often mix up when the assignment operator vs copy constructor are used, but it’s fairly straightforward:

- If a new object has to be created before the copying can occur, the copy constructor is used (note: this includes passing or returning objects by value).
- If a new object does not have to be created before the copying can occur, the assignment operator is used.

By default, the copy constructor and assignment operators provided by the compiler do a memberwise initialisation or assignment, which is a shallow copy. If your class dynamically allocates memory, this will likely lead to problems, as multiple objects will end up pointing to the same allocated memory. In this case, you’ll need to explicitly define these in order to do a deep copy. Even better, avoid doing your own memory management if you can and use classes from the standard library.


See also:
- [learncpp.com](https://learncpp.com) for the above summary and further details