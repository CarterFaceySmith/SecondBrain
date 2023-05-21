Using [[Entanglement]] we can create a protocol for quantum communication by manipulating the [[Qubits]] with [[Quantum Logic Gates]].

The key with this is that with classical computing there is a limit to the information transfer, naturally it's $n$ bits, and this is the same for [[Quantum Computing]] *buuut* we can use push this with [[Entanglement]].

E.g. Transferring one qubit can allow a two bit message to be sent, fucking crazy right?

## Let's step through this

Enter Alice and Bob, Alice wants to send a two bit message to Bob using qubits.

Sure she could just send two qubits, using them to encode the bit values and applying a $cx$ (X) gate to flip them for a 1 state.

	MSG = '00'
	qc_alice = QuantumCircuit(2,2)
	if MSG[-1]=='1':
		qc_alice.x(0)
	if MSG[-2]=='1':
		qc_alice.x(1)

Bob then measures these qubits.

	from qiskit import Aer
	backend = Aer.get_backend('aer_simulator')
	qc_bob = QuantumCircuit(2,2)
	qc_bob.measure([0,1],[0,1])
	backend.run(qc_alice.compose(qc_bob)).result().get_counts()

This results in **exactly** what Alice put in.

Let's go a little further, and entangle some shit.

Alice decides to add a $h$ and $cx$ gates ([[Quantum Logic Gates]]) after encoding the information.

	MESSAGE = '00'
	qc_alice = QuantumCircuit(2,2)
	if MESSAGE[-1]=='1':
	    qc_alice.x(0)
	if MESSAGE[-2]=='1':
		qc_alice.x(1)
	qc_alice.h(1)
	qc_alice.cx(1,0)

But then disentangles them by undoing the new logic gates.

	qc_bob = QuantumCircuit(2,2)
	qc_bob.cx(1,0)
	qc_bob.h(1)
	qc_bob.measure([0,1],[0,1])

You can see here that the parameters for the gates need to be the same and the order of the gates is reversed. Of note is that Alice could in fact entangle first then use gates to encode the correct message.

	MESSAGE = '00'
	qc_alice = QuantumCircuit(2,2)
	qc_alice.h(1)
	qc_alice.cx(1,0)
	if MESSAGE[-2]=='1':
	    qc_alice.z(1)
	if MESSAGE[-1]=='1':
	    qc_alice.x(1)

This doesn't matter to Bob, since he is receiving the same message his circuit doesn't need to change.

### Something very freaky

Because the gates can be applied to a single qubit, Alice can send qubit 0 to Bob as soon as the pair is entangled, and in fact she could send it before she even knows the message she wants to send.

Let's imagine a third party named Charlie, who just creates entangled states ($|\phi^+>$ ) and sends them.

	qc_charlie = QuantumCircuit(2,2)
	qc_charlie.h(1)
	qc_charlie.cx(1,0)

If this dude sends a qubit to Bob and then the other to Alice, Alice can encode her two qubit message by manipulating just this single qubit and then sending it on to Bob.

Bob then decodes this as before for the same message.

The result being, Alice has sent two *bits* of information to Bob and only had to send one qubit to do it, because the qubit was part of an *entangled* pair, when Alice applied gates to the one qubit she was mainpulating the larger set of four possible states the qubit pair could be in, effecting the other qubit as well despite never coming into contact with it directly.

Let's now take our friends here and throw another situation at you.

Enter [[The Hardy Paradox]].