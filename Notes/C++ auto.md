Automatic variable type deduction at [[Compilation]] time.

E.g. `auto x = "Carter"`

An interesting use case is the changing of function return types, by setting the declared assignment variable to `auto` we can automatically handle the changed return via type inference, as long as the code using that variable still works.

*Be careful with this*. Further, being able to know the type of something by reading the code is also important and often less error-prone.

Better used with iterators: `for(auto it = strings.begin(); it != strings.end(); it++)`, if you can't use a `foreach` or range-based loop, i.e. in older C++ versions.

Note: It is important to remember to use `const auto &<your variable>` ([[Pass-by-reference]]) to avoid copying the entire variable you are attempting to assign or whatever, if you have a massive vector this is crucial.


See also:
- [[C++]]
- [The "auto" keyword in C++](https://www.youtube.com/watch?v=2vOPEuiGXVo)
- [[Compiler]]