# Greedy Technique/Algorithms

[[Algorithms]] are typically designed to achieve the most optimal solution for the given problem, but in a greedy approach the closest solution from the possible solution doman is chosen if it *seems* to provide an optimum solution. I.e. this approach gives a *localised* optimum solution, not a global one taking into account external factors etc.

#### The Counting Coins Problem Example

>## Counting Coins
>
>This problem is to count to a desired value by choosing the least possible coins and the greedy approach forces the algorithm to pick the largest possible coin. If we are provided coins of ₹ 1, 2, 5 and 10 and we are asked to count ₹ 18 then the greedy procedure will be −
>
>-   **1** − Select one ₹ 10 coin, the remaining count is 8
>
>-   **2** − Then select one ₹ 5 coin, the remaining count is 3
>    
>-   **3** − Then select one ₹ 2 coin, the remaining count is 1
>    
>-   **4** − And finally, the selection of one ₹ 1 coins solves the problem
>    
>
>Though, it seems to be working fine, for this count we need to pick only 4 coins. But if we slightly change the problem then the same approach may not be able to produce the same optimum result.
>
>For the currency system, where we have coins of 1, 7, 10 value, counting coins for value 18 will be absolutely optimum but for count like 15, it may use more coins than necessary. For example, the greedy approach will use 10 + 1 + 1 + 1 + 1 + 1, total 6 coins. Whereas the same problem could be solved by using only 3 coins (7 + 7 + 1)
>
>Hence, we may conclude that the greedy approach picks an immediate optimized solution and may fail where global optimization is a major concern."