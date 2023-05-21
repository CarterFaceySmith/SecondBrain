# Shell Sort

A highly efficient sorting algorithm based on [[Insertion Sort]], average and worst-case time complexity of the algorithm depending on the gap sequence (this algorithm uses intervals to space the data for sorting using Knuth's Formula) but is usually O(n).

#### Woah Carter, this one sounds gnarly, what's going on

Nah mate, it's honestly fine, let's explain.

We take an array, unsorted of course, take an interval using Knuth's Formula (for the sake of simplicity we're gonna say it's 4 here), then make a sublist of all the values located at the interval of 4 positions.

We then compare these values in each sublist and swap them in the original array if necessary, we then take the interval of 1 and repeat that process until the array is sorted.


See also:
- [[Algorithms]]