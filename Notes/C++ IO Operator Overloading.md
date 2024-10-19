For classes that have multiple member variables, printing each of the individual variables on the screen can get tiresome fast. For example, consider the following class:

```cpp
class Point
{
private:
    double m_x{};
    double m_y{};
    double m_z{};

public:
    Point(double x=0.0, double y=0.0, double z=0.0)
      : m_x{x}, m_y{y}, m_z{z}
    {
    }

    double getX() const { return m_x; }
    double getY() const { return m_y; }
    double getZ() const { return m_z; }
};
```

If you wanted to print an instance of this class to the screen, you’d have to do something like this:

```cpp
Point point { 5.0, 6.0, 7.0 };

std::cout << "Point(" << point.getX() << ", " <<
    point.getY() << ", " <<
    point.getZ() << ')';
```

A rookie works around this by making a print function that defines a formatted output string based on the class, but because these are generally void functions they can't be called in the middle of an output statement.

## Overloading Operator<< or >>

Consider the expression `std::cout << point`. If the operator is <<, what are the operands? 

The left operand is the std::cout object, and the right operand is your Point class object. std::cout is actually an object of type std::ostream. Therefore, our overloaded function will look like this:

```cpp
// std::ostream is the type for object std::cout
friend std::ostream& operator<< (std::ostream& out, const Point& point);
```

Example implementation:

```cpp
#include <iostream>

class Point
{
private:
    double m_x{};
    double m_y{};
    double m_z{};

public:
    Point(double x=0.0, double y=0.0, double z=0.0)
      : m_x{x}, m_y{y}, m_z{z}
    {
    }

    friend std::ostream& operator<< (std::ostream& out, const Point& point);
};

std::ostream& operator<< (std::ostream& out, const Point& point)
{
    // Since operator<< is a friend of the Point class, we can access Point's members directly.
    out << "Point(" << point.m_x << ", " << point.m_y << ", " << point.m_z << ')'; // actual output done here

    return out; // return std::ostream so we can chain calls to operator<<
}
```

The trickiest part here is the return type. With the arithmetic operators, we calculated and returned a single answer using [[Pass-by-value]] (because we were creating and returning a new result). 

However, if you try to return std::ostream by value, you’ll get a compiler error. This happens because std::ostream specifically disallows being copied. In this case, we return the left hand parameter as a reference. This not only prevents a copy of std::ostream from being made, it also allows us to “chain” output commands together, such as `std::cout << point << std::endl;`

### >> 

Honestly the same except >> is an object of std::istream.

```cpp
// note that parameter point must be non-const so we can modify the object
// note that this implementation is a non-friend
std::istream& operator>> (std::istream& in, Point& point)
{
    double x{};
    double y{};
    double z{};

    in >> x >> y >> z;

    if (in)                     // if all input succeeded
        point = Point{x, y, z}; // overwrite our existing point

    return in;
}
```

### Guarding Against Partial Extraction

You might have expected to see our overloaded `operator>>` for `Point` implemented more like this:

```cpp
// Assume this operator is a friend of Point so we can directly access the members of point
std::istream& operator>> (std::istream& in, Point& point)
{
    // This version subject to partial extraction issues
    in >> point.m_x >> point.m_y >> point.m_z;

    return in;
}
```

However, this implementation may result in a partial extraction. Consider what would happen if the user were to enter “3.0 a b” as input. 3.0 would be extracted to `m_x`. The extraction to `m_y` and `m_z` would both fail, meaning `m_y` and `m_z` would be set to `0.0`. Our `point` would be partially overwritten by input and partially zero’d.

With a Point object, that might be an acceptable outcome. But imagine we were inputting a [[Fraction]] instead. A failed extraction to the denominator would set the denominator to `0.0`, which might later cause a divide by zero.

For this reason, it’s better to store all inputs until we can validate that all inputs were successful, and only then overwrite the object.
