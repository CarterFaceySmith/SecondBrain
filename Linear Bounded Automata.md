# Linear Bounded Automata

A multi-tape non-deterministic [[Turing Machines]] with a tape of some bounded finite length.

## Key Notes

- Length - function (Length of the initial input string, constant c)
- Memory information $\leq$ c x input information

Computation restricted to bounded area, input alphabet contains two special symbols which serve as left and right end markers, meaning the transitions dont move to the left or right end marker of the tape.

## Mathematical Definition

$$(Q, X, \Sigma, q_0, ML, MR, \delta, F)$$
-   **Q** is a finite set of states
-   **X** is the tape alphabet
-   **∑** is the input alphabet
-   **q0** is the initial state
-   **ML** is the left end marker   
-   **MR** is the right end marker where MR ≠ ML
-   **δ** is a transition function which maps each pair (state, tape symbol) to (state, tape symbol, Constant ‘c’) where c can be 0 or +1 or -1
-   **F** is the set of final states


Note:
- A deterministic linear bounded [[Automata]] is always context-sensitive
- A linear-bounded automata with empty language is undecidable

See also:
- 