This note is in the context of [[C++]].

Typecasting is the conversion of a data object from one type to another in a strongly typed programming language.

Related to [[C++ Type Punning]].

Can be implicit (`int val = 1; double val2 = val`;) or explicit (`double val2 = (double)val1;`). Explicit casts are sometimes called [[C]] style casts.

C++ style casts are casts as follows: `double s = static_cast<int>(value);`

## C++ cast types

- `static`: See above example
- `reinterpret`: Interpret existing [[Memory]] as a different type (see [[C++ Type Punning]])
- `dynamic`: See [[C++ Dynamic Casts]]
- `const`: Add remove *const* to something

The other C++ casts cannot do anything that cannot be done by C style casts, they are mainly syntactic sugar and checking (see [[C++ Dynamic Casts]]).


See also:
- [[Computer Science Fundamentals]]

