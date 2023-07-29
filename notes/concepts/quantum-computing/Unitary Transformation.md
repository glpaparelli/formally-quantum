This part is from [[Towards a Quantum Programming Language]]. 

[[Unitary Operator#Unitary Matrix|Unitary Matrices]], [[Linear Operator]]s

There are two kinds of operations by which we can manipulate a quantum state: **unitary transformations** and [[Measurement]]s. 

**The state of a quantum system can be transformed by applying a unitary transformation to it.** 
For instance, consider a [[Qubit]] in state $u = \alpha|0\rangle + \beta|1\rangle$, and let $S$ be a unitary $2\times 2$ matrix. 
The  we can perform the operation $$\begin{bmatrix}\alpha \\ \beta\end{bmatrix}\rightarrow S\begin{bmatrix}\alpha \\ \beta\end{bmatrix}$$Similarly, if $v = \alpha|00\rangle + \beta|01\rangle + \gamma|10\rangle + \delta|11\rangle$ is the state of a two-qubit quantum system, we can transform it by a unitary $4 \times 4$ matrix, and similarly for three or more quantum bits. 

A unitary operation on $n$ quantum bits is also known as $n-$ary [[Quantum Gate]]. 
While every unitary matrix can be realized in principle, one usually assume a fixed finite set of gates that are built in into the hardware. 
The particular choice is not important because the compiler will be able to translate such set to another. 
One possible choice is the following, which consists in four unary and five binary gates:
- [[Pauli Gates - X, Y, Z#X Gate|NOT Gate]]
- [[Hadamard Gate]]
- [[V Gate]]
- [[W Gate]]
- [[CNOT Gate]]
	- [[CV Gate]]
	- [[CW Gate]]
	- [[CHadamard Gate]]
- [[X Gate]]

Unitary transformations can be used to create quantum [[Quantum Mechanics Phenomenas#Superposition|superpositions]], and they can also be used to create entanglement between qubits. 
For example, the [[Hadamard Gate]], when applied to the classical state $|0\rangle$ creates a quantum superposition $\frac{1}{\sqrt2}|0\rangle + \frac{1}{\sqrt2}|1\rangle$. 
Also, the [[CNOT Gate]], applied to two independent quantum bits $(\frac{1}{\sqrt2}|0\rangle + \frac{1}{\sqrt2}|1\rangle)\bigotimes |0\rangle$, creates an entangled state $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|11\rangle$. 

A quantum gate can be applied in the presence of additional quantum bits. 
For example, to apply a unary gate $S$ to the second qubit in a $4$-bit system, we transform the system by the matrix $I \bigotimes S \bigotimes I \bigotimes I$, here $I$ is the $2\times 2$ identity matrix. 

# Todo 
stuff
#### Proposition 3.2