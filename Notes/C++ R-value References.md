Related to [[C++ L-value References]].

An r-value reference is a reference that is designed to be initialised with an r-value (only). While a  [[C++ L-value References]] reference is created using a single ampersand, an r-value reference is created using a double ampersand:

```cpp
int x{ 5 };
int& lref{ x }; // l-value reference initialized with l-value x
int&& rref{ 5 }; // r-value reference initialized with r-value 5
```

R-values references cannot be initialised with l-values.

## Why Do We Care?

1. They extend the lifespan of the object they are initialised with to the lifespan of the r-value reference
2. Non-[[C++ const]] r-value refs can let you modify the r-value.

```cpp
#include <iostream>

class Fraction
{
private:
	int m_numerator { 0 };
	int m_denominator { 1 };

public:
	Fraction(int numerator = 0, int denominator = 1) :
		m_numerator{ numerator }, m_denominator{ denominator }
	{
	}

	friend std::ostream& operator<<(std::ostream& out, const Fraction& f1)
	{
		out << f1.m_numerator << '/' << f1.m_denominator;
		return out;
	}
};

int main()
{
	auto&& rref{ Fraction{ 3, 5 } }; // r-value reference to temporary Fraction

	// f1 of operator<< binds to the temporary, no copies are created.
	std::cout << rref << '\n';

	return 0;
} // rref (and the temporary Fraction) goes out of scope here
```

This program prints: `3/5`

As an anonymous object, Fraction(3, 5) would normally go out of scope at the end of the expression in which it is defined. However, since we’re initialising an r-value reference with it, *its duration is extended until the end of the block*. We can then use that r-value reference to print the Fraction’s value.

## R-value References as [[Functions]] Parameters

Common use case, good for [[Function Overloading]] when you need different behaviour for l-value and r-value arguments.

```cpp
#include <iostream>

void fun(const int& lref) // l-value arguments will select this function
{
	std::cout << "l-value reference to const: " << lref << '\n';
}

void fun(int&& rref) // r-value arguments will select this function
{
	std::cout << "r-value reference: " << rref << '\n';
}

int main()
{
	int x{ 5 };
	fun(x); // l-value argument calls l-value version of function
	fun(5); // r-value argument calls r-value version of function

	return 0;
}
```

This prints:
```
l-value reference to const: 5
r-value reference: 5
```

When passed an l-value, the overloaded function resolved to the version with the l-value reference. 

When passed an r-value, the overloaded function resolved to the version with the r-value reference (this is considered a better match than an l-value reference to const).

### Returning an R-value Reference

You should almost never return an r-value reference, for the same reason you should almost never return an l-value reference. In most cases, you’ll end up returning a hanging reference when the referenced object goes out of scope at the end of the function.


See also:
- [R-value References - Learn CPP](https://www.learncpp.com/cpp-tutorial/rvalue-references/)