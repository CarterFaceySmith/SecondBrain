A sorting technique based on the divide-and-conquer approach, with a worst-case time complexity of O(n log n). 

The array/data structure is first divided into equal halves and then recombined in a sorted manner.

Basically, the array is broken down until each subarray is a single item, we then compare the elem for each subarray and recombine them into a new subarray in a sorted manner, so the next subarray sizes are two, then four, then eight etc until the final array is made and now sorted.


See also:
- [[Algorithms]]