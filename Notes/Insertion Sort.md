# Insertion Sort

An 'in-place' comparison-based sorting algorithm, a sub-list is maintained which is always sorted (eg let's say the lower half of the array is known to be sorted already or has been by the algorithm at this stage), an element is then taken from the initial array and inserted in its correct place in the sub-array (in the same overall array of course, you don't create an entirely new array).

Again, not amazingly efficient with an average and worst-case time complexity of O(n^2).


See also:
- [[Algorithms]]