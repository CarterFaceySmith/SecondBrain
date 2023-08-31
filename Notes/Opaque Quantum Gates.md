An opaque [[Quantum Logic Gates]] is simply a gate defined elsewhere with intake parameters which is then used in a subsequent circuit in an opaque fashion, i.e. the local code doesn't really know the configuration of the gate.

## [[Qiskit]] Example
```
from qiskit.circuit import Gate

my_gate = Gate(name='my_gate', num_qubits=2, params=[]) #Defined here

qr = QuantumRegister(3, 'q')
circ = QuantumCircuit(qr)
circ.append(my_gate, [qr[0], qr[1]]) #Used here, hypothetically in different code or waaaay down the line
circ.append(my_gate, [qr[1], qr[2]])

circ.draw()
```


