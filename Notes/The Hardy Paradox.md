Three people, Alice, Bob and Charlie.

Charlie packages a pair of shapes each day and send one to Alice and the other to Bob, who then compare what they've received. They look at two things, is it blue, and is it a cube.

After a few days they notice the never both have a cube, and that if one is not blue the other is always a cube.

There is obviously some sort of correlation between the two objects.

Alice and Bob imagine they both look at the colour and they find that their shape is not blue, Bob is then able to say Alice's shape is definitely a cube and Alice could do the same, but this breaks the theory that they never both have a cube. They then conclude that one of their shapes will always be blue.

Bit weird, right? There are limits to correlations possible with classical systems. *But that changes when we introduce [[Quantum Mechanics]]*.

## Enter, Qubits

When you're extracting information from qubits we do this via measurement, the method of which depends on the details of how your qubit is built, we can do different kinds of measurement to get different results.

Standardly though, we can simply rotate the qubit itself. By performing single qubit gates before marking a standard measurement we reproduce the effects of alternative forms of measurement.

Common implementation: Apply an $h$-gate immediately before measurement, this gives us something known as an *x measurement*.

### [[Qiskit]] Example

```python
	meas_x = QuantumCircuit(1,1)
	meas_x.h(0)
	meas_x.measure(0,0)
```

Standard measurement done with just a measure gate is known as *z measurement*.

```python
	meas_z = QuantumCircuit(1,1)
	meas_z.measure(0,0)
```

## [[The Uncertainty Principle]]

