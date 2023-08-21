# Pushdown [[Automata]]

Think Finite State Automata + the [[Stack]].

Input string accepted if execution finshes in an accepting state *and* the stack is empty.

### Mathematical definition 
$$
M =\ <Q, \Sigma, \Lambda, \delta, q_0, F>
$$
#### Deterministic
Q = the possible states, normally written as Q0, Q1... (finite)
$\Sigma$ = the *input* alphabet of M
$\Lambda$  = the *stack* alphabet of M
$Q_0$ = the starting state of M
$F \subseteq Q$ = Final states (AKA accept states), a subset of all possible states
$\delta$ = the set of transitions in M

See also:
- [[Automata]]
- 