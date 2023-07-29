To perform operations on [[Qubit]]s we require quantum gates. 
Quantum gates are essentially evolutions of quantum states.
In the circuit model they can be treated as black boxes.

Quantum gates have the property that have an equivalent number of inputs and outputs. 
This stems specifically from the fact that quantum mechanics is a theory that obeys time symmetry. 
A quantum mechanical system that is evolved from a given initial state to a finite state using a definite series of operations can be evolved backwards from the final state to the initial state using the inverse of the series of operations on it. 

**A quantum computer is also a reversible machine.** 
A gate operating on an input to turn it into an output will not be able to do the reverse if the number of outputs are smaller than the number of inputs because information would be lost in the process. 
Hence the equivalence of the number of inputs and outputs.
We can divide quantum gates into categories based on the number of inputs/outputs. 

To represent the operation of particular gates we use matrices. 
Since the state of a qubit register can be given by kets or column matrices, operations on them can be represented by square matrices. 
**Multiply an input state column matrix with the matrix for the quantum gate, we obtain the output state.**
This scheme makes conceptualizing quantum computing easier. 

### Single Qubit Operations
The simplest quantum gates are single qubit gates. 
The [[Identity Gate]], the [[Pauli Gates - X, Y, Z]]s and the [[Hadamard Gate]] are [[Unitary Transformation]]s.