Let's say you wanna get fucking kooky, let's say you wanna get a little *unhinged* and explore more of life's intricacies. Sure you could do drugs, but why when building one of these can have the same effect?

A parameterised quantum circuit is a quantum circuit that takes in some value, ie the parameter you fucking idiot, maybe it's a looping incrementer, maybe it's your mother's favourite rgb value, who knows and who cares.

## [[Qiskit]] Example

```python
from qiskit.circuit import Parameter

theta = Parameter('θ')

n = 5

qc = QuantumCircuit(5, 1)

qc.h(0)
for i in range(n-1):
    qc.cx(i, i+1)

qc.barrier()
qc.rz(theta, range(5))
qc.barrier()

for i in reversed(range(n-1)):
    qc.cx(i, i+1)
qc.h(0)
qc.measure(0, 0)

qc.draw('mpl')
```

These parameters need to be __bound__ before they can be sent to a backend, this is normally done by dictionary mapping the parameters to values and returning a new circuit with each replaced by its corresponding value, partial binding can be done but the circuit is parameterised for any parameters that were not mapped to a value.

```python
import numpy as np

theta_range = np.linspace(0, 2 * np.pi, 128)

circuits = [qc.bind_parameters({theta: theta_val})
            for theta_val in theta_range]

circuits[-1].draw()
```

## Composition/Joining

You can compose these guys just like regular circuits basically, the resulting circuit is parameterised by the union of the parameters of the input circuits.

## Notes
- Parameter names must be distinct within a given circuit if you do a composition of more than one
- It is often effective to compile over a parameterised circuit prior to binding so that compilation time can be reduced compared to compiling over a set of bound circuits