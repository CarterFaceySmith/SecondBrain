Comparable to a more powerful form of [[Generics]] in other languages.

A template let's you define a template that will be compiled based on your usage, the [[Compiler]] compiles it based on rules you give it, it's sort of like a blueprint.

An example use case for this might be when you want to use [[Functions]] with different input types and the same output without writing a bunch of overloads.

Example for a print function:

```c++
template<typename T>
void print(T value){
	std::cout << value << std::endl;
}

int main(){
	print<int>(1); /* You can define the input type in the call */
	print("Carter"); /* Or let the compiler implicitly deduce it */
}
```

With templates, you must either write *and* use them inside a *single* source (`.cpp`) file, *or* you must write them *entirely* inside a header file. 

Unlike a regular function or class, you can *not* declare them inside a header file and then define them inside a source file. [[Linkers]] won't be able to link the templates if you do.

Another example, this time comparing for a minimum.

```c++
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

There is no practical limit to the number of type parameters. Separate multiple parameters by commas:

```C++
template <typename T, typename U, typename V> class Foo{};
```

The keyword class is equivalent to typename in this context. You can express the previous example as:

```C++
template <class T, class U, class V> class Foo{};
```

You can use the ellipsis operator (...) to define a template that takes an arbitrary number of zero or more type parameters:

```C++
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

Any built-in or user-defined type can be used as a type argument. For example, you can use std::vector in the Standard Library to store variables of type `int`, `double`, `std::string`, `MyClass`, `const MyClass*`, `MyClass&`, and so on. 

The primary restriction when using templates is that a type argument ***must*** support any operations that are applied to the type parameters.

## Templates and classes

We can templatise the definition of classes as well, exciting stuff.
```c++
template<typename T, int N>
class Array{
	private:
		T m_array[N]; /* Compile-time defined array of type T size N */
	public:
		int getSize() const {return N;}
}

int main(){
	Array<5> array;
	std::cout << array.getSize() << std::endl;
}
```

Going *even further*, we can use a template **as** as template parameter:

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## Default arguments for templates

You can define default args for a template, when a template has default args you can leave it unspecified when used.

```cpp
template<typename A = int, typename B = double>
class Bar
{
    //...
};
...
int main()
{
    Bar<> bar; // use all default type arguments
}
```

## Template specialization

What if you don't want the template to define the exact same code for any type, then you can use a specialization of the template for that type. The [[Compiler]] will automatically use that specialization when the user instantiates the template with that type.

A template can have any number of specializations as long as each type parameter is unique, only class templates can be partially specialized, and all specializations of a template must be declared in the same namespace as the original template.

```cpp
template <typename K, typename V>
class MyMap{/*...*/};

// partial specialization for string keys
template<typename V>
class MyMap<string, V> {/*...*/};
...
MyMap<int, MyClass> classes; // uses original template
MyMap<string, MyClass> classes2; // uses the partial specialization
```

Further: [Template Specialization - Microsoft Learn](https://learn.microsoft.com/en-us/cpp/cpp/template-specialization-cpp?view=msvc-170)


See also:
- [[C++]]
- [[Generics]]
- [[Metaprogramming]]
- [[Optimisation]]
- [Templates - cppreference](https://en.cppreference.com/w/cpp/language/templates)
- [Templates - Microsoft Learn](https://learn.microsoft.com/en-us/cpp/cpp/templates-cpp?view=msvc-170)