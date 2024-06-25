A declaration which appears in a class body to grant a [[Functions]] or another class access to private or protected members of the class it the friend declaration appears in.

```cpp
class Y
{
    int data; // private member
 
    // the non-member function operator<< will have access to Y's private members
    friend std::ostream& operator<<(std::ostream& out, const Y& o);
    friend char* X::foo(int); // members of other classes can be friends too
    friend X::X(char), X::~X(); // constructors and destructors can be friends
};
 
// friend declaration does not declare a member function
// this operator<< still needs to be defined, as a non-member
std::ostream& operator<<(std::ostream &out, const Y& y)
{
    return out << y.data; // can access private member Y::data
}
```
