Declarator operators are when standard operators are used in an argument declaration, this changes their meaning, for example in [[C++]]:

- T a[n] means a is an [[Arrays]] of n Ts
- T * p means p is a [[Pointer]] to T
- T & r means r is a [[C++ R-value References]] to T
- T f(A) f is a [[Functions]] taking an argument of type A and returning a result of type T 