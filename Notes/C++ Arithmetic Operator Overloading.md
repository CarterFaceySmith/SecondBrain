The four arithmetic operators (+, -, * and /) are all binary [[C++]] operators (take two args), which can overloaded the same ways.

## Overloading Using [[C++ friend]] [[Functions]]

```cpp
#include <iostream>

class Cents
{
private:
	int m_cents {};

public:
	Cents(int cents) : m_cents{ cents } { }

	// add Cents + Cents using a friend function
	friend Cents operator+(const Cents& c1, const Cents& c2);

	int getCents() const { return m_cents; }
};

// note: this function is not a member function!
Cents operator+(const Cents& c1, const Cents& c2)
{
	// use the Cents constructor and operator+(int, int)
	// we can access m_cents directly because this is a friend function
	return c1.m_cents + c2.m_cents;
}
```

### Friend Functions Can Be Defined Inside the Class 

```cpp
#include <iostream>

class Cents
{
private:
	int m_cents {};

public:
	explicit Cents(int cents) : m_cents{ cents } { }

	// add Cents + Cents using a friend function
        // This function is not considered a member of the class, even though the definition is inside the class
	friend Cents operator+(const Cents& c1, const Cents& c2)
	{
		// use the Cents constructor and operator+(int, int)
		// we can access m_cents directly because this is a friend function
		return Cents { c1.m_cents + c2.m_cents };
	}

	int getCents() const { return m_cents; }
};
```

*What about for different types?* Check the following, noting they both are overloaded versions of the same func. to take parameter ordering into account, no other differences.

```cpp
// note: this function is not a member function!
Cents operator+(const Cents& c1, int value)
{
	// use the Cents constructor and operator+(int, int)
	// we can access m_cents directly because this is a friend function
	return Cents { c1.m_cents + value };
}

// note: this function is not a member function!
Cents operator+(int value, const Cents& c1)
{
	// use the Cents constructor and operator+(int, int)
	// we can access m_cents directly because this is a friend function
	return Cents { c1.m_cents + value };
}
```

## The Second Way: Normal Function

For when you don't really need access to internal members of the classes you're operating on.

```cpp
#include <iostream>

class Cents
{
private:
  int m_cents{};

public:
  Cents(int cents)
    : m_cents{ cents }
  {}

  int getCents() const { return m_cents; }
};

// note: this function is not a member function nor a friend function!
Cents operator+(const Cents& c1, const Cents& c2)
{
  // use the Cents constructor and operator+(int, int)
  // we don't need direct access to private members here
  return Cents{ c1.getCents() + c2.getCents() };
}
```

>"Because the normal and friend functions work almost identically (they just have different levels of access to private members), we generally won’t differentiate them. The one difference is that the friend function declaration inside the class serves as a prototype as well. With the normal function version, you’ll have to provide your own function prototype."

### Best Practice Note

>"In general, a normal function should be preferred over a friend function if it’s possible to do so with the existing member functions available (the less functions touching your classes’s internals, the better). However, don’t add additional access functions just to overload an operator as a normal function instead of a friend function!"

## [[C++ IO Operator Overloading]]