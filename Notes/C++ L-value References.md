Prior to [[C++11]], only one type of reference existed in [[C++]], and so it was just called a “reference”. However, in C++11, it’s called an l-value reference. L-value references can only be initialised with modifiable l-values.

L-value references to [[[C++ const]]] objects can be initialised with modifiable and non-modifiable l-values and r-values alike. However, those values can’t be modified.

````cpp
int& lref{ x }; // l-value reference initialized with l-value x
````
