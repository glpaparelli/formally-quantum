We use the [[Dirac Notation]] to represent vectors.

In the [[The Circuit Model of Computation]] context we have discrete [[Quantum Gate]]s being applied to cause discrete changes in the quantum state. 
We will consider only discrete computational steps, hence the second postulate can be simplified. 

> The discrete time evolution of a closed quantum system is described by a **[[Unitary Operator]]**. 
> The state $|\psi\rangle$ of a system at a time $t_1$ is related to the state $|\psi\rangle'$ of the system at a later time $t_2$ by a unitary matrix $U$ which depends only on the times $t_1$ and $t_2$: $|\psi\rangle' = U|\psi\rangle$   

Remarks: 
- this expression follows directly from the Schroendinger's equation: every unitary operator $U$ can be realized as a solution of Schroendinger's equation. 
- the postulate does no tell us **which unitary matrix transformation** describe real-world quantum dynamics: they need to be figured out case by case
- **why unitary matrix?**
	- unitary matrix are the only matrices which **preserve length**
	- we want the quantum state to remain normalized, so that the probabilities of measurement outcomes sum to one