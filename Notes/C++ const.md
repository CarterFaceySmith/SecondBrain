`const` is a  [[Compilation]] time constraint that an object cannot be modified, makes a variable/object read-only.

When used with pointers (e.g. `const int *p1 = &i;`) the data is const but the [[Pointer]] is not, you can make the pointer `const` by doing something like `int* const p2` to make the data mutable but the pointer immutable.

To make the pointer and data both `const` we do something like `const int* const p3`.

Put simply: *if const is on the left of *, data is const, otherwise pointer is const*.

We can also use [[Typecasting]] to convert a non-const data structure to const or vice versa: `static_cast<const int&>(j) = 7`, but this is a very dangerous way of programming, especially in larger codebases.

## Why Use It?

- Guards against inadvertent writes to the variable
- Self-documenting code
- [[Compiler]] can do further [[Optimisation]] measures
- Allows the variable to be put in read-only [[Memory]]

## `const` With Functions

There are three ways to use `const` with a function:
- `const` parameter
- `const` return value
- `const` function

Note, a `const` function *can only call another `const` function to maintain the const-ness*. 

Although, you can use [[Function Overloading]] to add a non-const variant for use, also a function that takes a `const` reference parameter (`void setAge(const int &a)`) can be overloaded with a function that takes a reference parameter (`void setAge(int &a)`).

## Logical `const`ness & [[Bitwise]] `const`ness




See also:
- [[C++]]