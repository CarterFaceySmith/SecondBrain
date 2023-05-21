An emerging field of computing that uses bleeding-edge tech to attempt to improve upon existing computing capabilities in certain areas, mainly those relating to exponential algorithms/intractable problems.

They pull this crazy shit off using qubits, a bit variant that uses quantum mechanics to represent any state of a bit simultaenously until measured, think [[Probability]]. This is called [[Superposition]], allowing groups of qubits to create wildly complex multi-dimensional computational spaces which we can represent problems in new ways in.

## How is [[Entanglement]] relevant here?

Yeah, sure, this is all well and good but why [[Quantum Mechanics]]?

Mainly because of the limitations of computing, keeping track of amplitudes up to $2^n$ for $n$ qubits requires exponential growth in the representative vectors. So instead we can begin with a [[Qubit Product States]], meaning each qubit can be independently described by a single qubit state with two amplitudes.

Now if we make a circuit with only single [[Qubits]] gates, these manipulations can be described by modifying the single qubit states which means making changes to the pairs of amplitudes affected. Then of course, when each qubit is measured the [[Probability]] of the outcome being 0 or 1 for each qubit is determined by their amplitudes.

Remember that during this process the states remained product states, and so there's never really any *combined* $n$-qubit computation but rather $n$ seperate qubit computations. This gives us $2n$ amplitudes to track, much more feasible.

But to be useful, [[Quantum Algorithms]] need to be able to go beyond classical computing, using the full $2^n$ amplitudes, so more than product states is needed, and *anything that isn't a product state is an entangled state*, entanglement becomes a requirement for [[Quantum Advantage]].

A great example of these concepts is in [[Quantum Communication]].


See also:
- [[Quantum Circuits]]
- [[Quantum Logic Gates]]
- [[Entanglement]] 
- [[Probability Amplitudes]]
- [[Theoretical Computer Science]]
- 
