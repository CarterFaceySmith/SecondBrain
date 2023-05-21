One of the [[Quantum Algorithms]].

Grover's Algorithm is used for [[Unstructured Search]], when searching any database (structured or unstructured) Grover's algorithm grows with the *square root* of the number of inputs, fuckin crazy.

This is a **_quadratic_** improvement over the **_best_** classical algorithm.

That is absolutely insane.

## [[Boolean Satisfiability Problems]] and Grover

You can change problems to fit a solver, basically problems come down to "find the input that results in a certain output".

A solution to a SAT problem is a string of bits, which makes it an easy map to [[Quantum Circuits]]. 

We use the Qiskit *PhaseOracle* function for this, which as you might expect changes the phase of the output state by $180\degree$ (ie multiply by -1) if the state is a solution.  

## That's great and all but what's the algorithm?

1. Create an equal [[Superposition]] of every possible input to the oracle, we call this equal superposition state $'|s>'$.
	1. If all qubits start in the 0 state we can create this by applying an $h$-gate to each, different start state configurations will require different actions I think
2. Run the oracle circuit ($U_{oracle}$) on the [[Qubits]]
3. Run a 'diffusion operator'/'diffuser' circuit ($U_s$) on the qubits
4. Repeat steps 2 and 3 a few times depending on the size of the circuit

See also:
- [[Algorithms]]
- [[Quantum Computing]]