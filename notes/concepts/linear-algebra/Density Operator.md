In quantum mechanics [[Mixed State]]s are described by **density matrices** or **density operators**, which are certain [[Trace-Class Operator]]. 

**A density matrix** (or density operator) **is a matrix that describes the quantum state of a physical system.** 
It allows for the calculation of the probabilities of the outcomes of any measurement performed upon this system. 

A **density operator** $\rho$ on a [[Hilbert Space]] $\mathcal{H}$ is defined to be a [[Positive Operator]] with [[Trace]] $tr(\rho) = 1$. 

Then a [[Mixed State]] of a quantum system with state space $\mathcal{H}$ is described by a density operator on $\mathcal{H}$. 

### Partial Density Operator
We now see a slightly generalized notion of the density operator: a **partial density operator** $\rho$ is a [[Positive Operator]] with $tr(\rho) \leq 1$. 
In particular, the zero operator is a partial density operator. 

The set of partial density operators is denoted $\mathcal{D}^{-}(\mathcal{H})$. 

A partial density operator can also be defined by an ensemble of [[Pure State]]s. 
Suppose that a quantum system is in one of a number of pure states $|\psi_i\rangle$, with respective probabilities $p_i$, where is required that $\Sigma_i p_i \leq 1$. 
Then $\rho=\Sigma_ip_i|\psi_i\rangle\langle\psi_i|$ is a partial density operator. 

The notion of partial density operator allows us to follow **Selinger's normalization convention** "we normalize each state in such a way that the sum of the squares of the amplitudes is equal to the total probability that this state is reached". 

The partial density operator can be used to describe the global state of quantum variables because it provides a way to calculate the reduced density matrix of a subsystem, which is a key quantity in many quantum information protocols. 
By analyzing the partial density operators of the subsystems, one can gain insights into the properties of the global state, such as its entanglement structure and its potential for quantum information processing.
