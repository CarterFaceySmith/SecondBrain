One of the [[Quantum Algorithms]].

Schöning’s algorithm chooses an input at random and checks if it works. But unlike random guessing, it doesn’t just throw this string away. 

It picks an unsatisfied clause and toggles a bit in the string to satisfy that clause. 

This might un-satisfy a different, previously-satisfied clause, but on average it's beneficial to keep toggling bits in this manner a few times. 

If the initial guess was close enough, there’s a fair chance we’ll stumble upon the correct solution. If not, then after some number of steps, the computer starts again with a new completely random guess. 

It turns out for 3-SAT ([[Boolean Satisfiability Problems]]) (although not (>3)-SAT), this algorithm grows with roughly , which not only beats random guessing, but also beats [[Grover's Search Algorithm]].

We can also combine Grover's and Schonings for even greater effectiveness, we do this by creating a [[Quantum Circuits]] that does the bit toggling and use this as the oracle then use Grover's to find the best 'initial guess'.

Fucking insane.


See also:
- [[Unstructured Search]]