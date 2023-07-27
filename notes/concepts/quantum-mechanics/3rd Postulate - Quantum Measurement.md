We use the [[Dirac Notation]] to represent vectors.

We postulated that closed quantum systems evolve according to a unitary operator. 

We will be interested in observing and measuring some properties of a system: at some point we must allow the system to interact must allow the system to interact with the measurement apparatus of some observer (an external physical system).
When this happens the original system is no longer closed, and the evolution postulate is no longer appropriate for describing its evolution. 
**The evolution of the state of a system during a measurement is not unitary.**

Quantum systems do get perturbed and modified as a result of measuring them. 
**Only the probability of observing specific values can be calculated: measurement is a non-deterministic process.** 

The third postulate provides a means for describing the effects of measurements of quantum systems. 
- It is a mathematical formalism for measurements
	- it does not tells us what measurement can be done in practice, or with what efficiency
	- some measurements can be simple to state mathematically, but not easy to employ
- it tells us how to compute the probability $p(m)$ that outcome $m$ occurs, and the new state of the system after the measurement with outcome $m$, applying the **measurement operators** $M_m$ (one operator for each outcome)

**Measurement Postulate:**
Quantum measurements are described by a collection $\{M_m\}$ of **measurement operators** that satisfy the **completeness relation** $$\Sigma_m(M_m^{\dagger}M_m) = I$$The index $m$ labels the measurement outcomes that may occur in the experiment.

If the state of the quantum system is $|\psi\rangle$ immediately before the measurement, then for each $m$
- the probability that result $m$ occurs is given by $$p(m) = \langle\psi|M^{\dagger}_m M_m|\psi\rangle = ||M_m|\psi\rangle||^2$$
- and the state of the system after the measurement with outcome $m$ is $$\frac{M_m|\psi\rangle}{\sqrt{\langle\psi|M^{\dagger}_m M_m|\psi\rangle}}$$

**Remarks**
- this is a mathematical formalism for measurements 
- the state of the system after the measurement is a properly **normalized quantum state** and in general is not a scalar multiple of $|\psi\rangle$: the measurement has modified the state of the system
- the denominator vanishes only if $p(m)=0$ (this outcome will never occur)
- the completeness equation express the fact that the probabilities sum up to one $$\Sigma_mp(m)= \Sigma_m \langle\psi|M^{\dagger}_mM_m|\psi\rangle= \langle\psi|I|\psi\rangle= \langle\psi|\psi\rangle= 1$$ where $|\psi\rangle$ is arbitrary and not dependent on the index $m$

#### Example: Single Qubit Measurement in the Computational Basis
In computer science, by measurement we often mean single [[Qubit]] measurement in the [[Computational Basis]] $\{|0\rangle, |1\rangle\}$. 
This measurement has two outcomes ($0$ and $1$) and the measurement operators are:
- $M_0 = |0\rangle\langle0| = \begin{bmatrix} 1 \\ 0\end{bmatrix}[1\ \ 0] = \begin{bmatrix}1 & 0 \\0 & 0\end{bmatrix}$ 
- $M_1 = |1\rangle\langle1| = \begin{bmatrix} 0 \\ 1\end{bmatrix}[0\ \ 1] = \begin{bmatrix}0 & 0 \\0 & 1\end{bmatrix}$ 

Each measurement operator is a **projector:** $M_0^2=M_0,\ M_1^2=M_1$ 
The completeness equation is satisfied: $$\Sigma_mM^{\dagger}M = M_0^{\dagger}M_0+M_1^{\dagger}M_1 = M_0 + M_1 = \begin{bmatrix}1 & 0 \\0 & 0\end{bmatrix}\begin{bmatrix}0 & 0 \\0 & 1\end{bmatrix} = I$$Assume our system is in the state $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$
According to the third postulate, the probability of obtaining the measurement outcome $0$ is $$p(0) = \langle\psi|M_0^{\dagger}M_0|\psi\rangle = \langle\psi|0\rangle\langle0|0\rangle\langle0|\psi\rangle = \langle\psi|0\rangle\langle0|\psi\rangle= \alpha^*\alpha=|\alpha|^2$$Similarly, the probability of obtaining the measurement outcome $1$ is $$p(1) = \langle\psi|M_1^{\dagger}M_1|\psi\rangle = \langle\psi|1\rangle\langle1|1\rangle\langle1|\psi\rangle = \langle\psi|1\rangle\langle1|\psi\rangle= \beta^*\beta=|\beta|^2$$
**The state after measurement** in the two cases is: 
- $\frac{M_0|\psi\rangle}{\sqrt{p(0)}} = \frac{|0\rangle\langle0|\psi\rangle}{|\alpha|}=\frac{\alpha}{|\alpha|}|0\rangle \equiv |0\rangle$
- $\frac{M_1|\psi\rangle}{\sqrt{p(1)}} = \frac{|1\rangle\langle1|\psi\rangle}{|\beta|}=\frac{\beta}{|\beta|}|1\rangle \equiv |1\rangle$

The factors $\frac{\alpha}{|\alpha|}$ and $\frac{\beta}{|\beta|}$ are [[Global Phase Factor]]
- $\alpha = |\alpha|e^{i\phi}$ for same phase angle $\phi \in [0, 2\pi] \rightarrow$ $\frac{\alpha}{|\alpha|} = e^{i\phi}$ 
- $\beta = |\beta|e^{i\gamma}$ for same phase angle $\gamma \in [0, 2\pi] \rightarrow$ $\frac{\beta}{|\beta|} = e^{i\gamma}$ 
Thus, these states can be regarded as equivalent to the quantum states $|0\rangle$, $|1\rangle$ respectively, as expected for a measurement in the computational basis. 
Thus: 
- **global phase have no observable consequences**
- this explains the claim that **global phase have no physical significance**

#### Projective Measurements
For many applications of quantum computation and quantum information, we will mostly perform **projective measurements.**
For these measurements, the measurement operators can be defined in terms of [[Hermitian Operator]]s. 

In physics, Hermitian operators are called **observables**
- an **observable is a property of a physical system**, i.e., a physical quantity that can be measured (e.g., position, polarization)
- each physical observable corresponds to an Hermitian operator $M$
- all [[Eigenvalues and Eigenvectors| Eigenvalues]] of an observable are real, and the [[Eigenvalues and Eigenvectors | Eigenvectors]] are orthogonal 
- the possible outcomes of a measurement correspond to the eigenvalues of the observable $M$
- the measurement operators can be derived from the spectral decomposition of the observable M

**Observables can be thought of as questions we can pose to quantum systems. 
Each question admits a set of answers: the eigenvalues of the observable.**

Any observable $M$ can be written as **spectral decomposition**
$$M = \Sigma_m mP_m = \Sigma_m m|u_m\rangle\langle u_m|$$
where: 
- $m$ are the real eigenvalues of $M$ (outcomes of the measurement)
- $|u_m\rangle$ is the eigenvector associated to $m$
- $P_m = |u_m\rangle\langle u_m|$ is the projector onto the eigenspace of $M$ with real eigenvalue $m$

The **measurement operators** are the **projectors** $P_m = |u_m\rangle\langle u_m|$ 
**Projectors** are operators $P$ which satisfy $P^2 = P$

An example of projector operator is the operator $|0\rangle\langle 0|$:
$$(|0\rangle\langle0|)^2 = |0\rangle\langle0||0\rangle\langle0|=|0\rangle\langle0|0\rangle\langle0| = |0\rangle\langle0|$$
since $\langle0|0\rangle = 1$ 


The possible outcomes of the measurement correspond to the **eigenvalues** $m$ of the observable
$$M = \Sigma \ mP_m = \Sigma \ m|u_m\rangle\langle u_m|$$
Upon measurement the state $|\psi\rangle$ the probability of getting the result $m$ is given by
$$p(m) = \langle \psi | P^\dagger_m P_m | \psi\rangle = \langle \psi|P_m|\psi\rangle$$
Given the outcome $m$ occurred, the state of the quantum system immediately after the measurement is $$\frac{P_m\psi_m}{\sqrt{p(m)}}$$The operators $P_m$ satisfy the completeness relation
$$\Sigma_m \ P_m^\dagger P_m = \Sigma_m P_m = I$$
Since all possible outcomes of a projective measurement are real numbers, we can compute the **expectations** (average value) of $M$ in state $|\psi\rangle$
$$
\begin{align}
E_\psi[M] =\\ \Sigma_m\ p(m) =\\ \Sigma_m m\langle\psi|P_m|\psi\rangle =\\ \langle\psi|\Sigma_m \ P_m|\psi\rangle = \\ \langle\psi|M|\psi\rangle 
\end{align}
$$
**Example:**
The [[Pauli Gates - X, Y, Z|Gate Z]] is a [[Hermitian Operator]] and can be interpreted as an observable
$$
Z = \begin{bmatrix} 1 & 0 \\ 0 & -1\end{bmatrix}
$$
**corresponding to measure the projection of the state vector of a qubit along the $z$-axis**
![[z-gate-observable.png | center | 300]]
Z has eigenvalues $+1$ and $-1$ with corresponding eigenvectors $|0\rangle$ and $|1\rangle$, and its decomposition is
$$Z = \begin{bmatrix} 1 & 0 \\ 0 & -1\end{bmatrix} = |0\rangle\langle0| - |1\rangle\langle1|$$
The measurement of Z on the state $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ gives: 
- the result $+1$ with probability $|\alpha|^2$ and the state after the measurement is $|0\rangle$
- the result $-1$ with probability $|\beta|^2$ and the state after the measurement is $|1\rangle$

#### Measurement in the Computational Basis
A measurement of a qubit in the $|0\rangle, |1\rangle$ basis corresponds to perform a projective measurement with projectors
$$
\begin{align}
P_0 = |0\rangle\langle0| = \begin{bmatrix} 1 \\ 0\end{bmatrix}\begin{bmatrix} 1 & 0\end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 0 & 0\end{bmatrix} \\ 
P_1 = |1\rangle\langle1| = \begin{bmatrix} 0 \\ 1\end{bmatrix}\begin{bmatrix} 0 & 1\end{bmatrix} = \begin{bmatrix} 0 & 0 \\ 0 & 1\end{bmatrix}
\end{align}
$$
**Observable?**
It can be viewed as a projective measurement with respect to the Hermitian matrix Z
$$
Z = \begin{bmatrix} 1 & 0 \\ 0 & -1\end{bmatrix} = |0\rangle\langle0| - |1\rangle\langle1|
$$ or also wrt the identity matrix with all eigenvalues equal to $1$
$$
I = \begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix} = |0\rangle\langle0| + |1\rangle\langle1|
$$

## Summary
This part is from the preliminary section of [[floyd-hoare-logic-for-quantum-programs]]. 
A quantum measurement on a system with state space $\mathcal{H}$ is described by a collection of $\{M_m\}$ [[Linear Operator]]s on $\mathcal{H}$ satisfying the following normalization condition, called **completement relation**: 
$$\Sigma_mM^\dagger_mM_m = I_\mathcal{H}$$
where $M_m$ are called **measurement operators**, and the index $m$ stands for the measurement outcomes that may occur in the experiment. 

If the state of the quantum system is in a pure state $|\psi\rangle$ immediately before the measurement, than for each $m$: 
- probability that result $m$ occurs is $$p(m)=\langle\psi|M^\dagger_m|M_m|\psi\rangle = ||M_m|\psi\rangle||^2$$
- the state of the system after the measurement is $$|\psi_m\rangle = \frac{M_m|\psi\rangle}{\sqrt{p(m)}}$$
We can also formulate the quantum measurement postulate in the language of [[Density Operator]]s. 
If the state of a quantum system is $\rho$ immediately before the measurement $\{M_m\}$ is performed on it, then the probability that result $m$ occur is $$p(m)=tr(M_m^\dagger M_m\rho)$$and the state of the system after the measurement is $$\rho_m= \frac{M_m\rho M^\dagger_m}{p(m)}$$
A special class of quantum measurement will be used frequently: if a measurement $M$ has only two outcomes, say $0$ and $1$; that is $M = \{M_0, M_1\}$, then we call $M$ a yes-no measurement. 