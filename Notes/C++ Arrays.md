The main difference between arrays in a lang like Java and arrays in C++ is bounds checking.

C++ arrays don't have automatic bounds checking, and as such the length cannot be checked with built in functions, more importantly, C++ won't stop you from checking/requesting index positions that don't exist in the array, causing a potential buffer overflow.

A buffer overflow is an incredibly bad mistake, it compromises the security of whatever you're working on. This occurs when a program, when writing data to a buffer, overruns the buffer's boundary and overwrites adjacent memory locations.

Look man, TLDR is this, arrays dont have bounds in [[C++]] and going outside the array length due to monkey brain stupidity is really fucking bad, so don't do that.

### Implemented bounds-checking and further functionality

We can use the at_ function to have implicit bounds checking, when trying to access an array position that is out of bounds this will throw an error as opposed to allowing access (to the programmer's detriment).

See the C++ documentation on the array container class for further implementation details and functionality.

### Passing arrays to a function

The whole array is not passed to a function, we pass a pointer to the first element of the array, we then make use of our index vals to get to any element of the array, fkn genius.

### Traversing an array

For loops are your friend.


### Notes
- Remember that the format when querying arrays is arrayname[row][column].