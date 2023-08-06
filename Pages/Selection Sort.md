# Selection Sort

A simple sorting algorithm, works 'in-place' comparison-based, the data structure is divided into a sorted and unsorted portion (the left and right side of the data structure respectively), initially the unsorted portion is just the entire structure.

The smallest elem is selected from the unsorted section, it is then swapped with the leftmost elem and that elem becomes part of the sorted section. This continues until the unsorted section is empty.

Not efficient, has an average and worst-case time complexity of O(n^2), with n of course being the total number of items.


See also:
- [[Algorithms]]