This part is from [[Towards a Quantum Programming Language]]

Now we introduce a better notation for [[Pure and Mixed States|mixed states]], which is due to von Neumann
First consider a pure state, represented as usual by a unit vector $\mathbf{u}$  (a vector with [[Norm]] $=1$).
In the von Neumann notation, this quantum state is represented by the matrix $\mathbf{u}\mathbf{u}^\top$, which is called **density matrix**.
For example the state of a [[Qubit]] $u = \frac{1}{\sqrt2}|0\rangle - \frac{1}{\sqrt2}|1\rangle$ is represented by the density matrix $$\mathbf{u}\mathbf{u}^\top =\begin{bmatrix}\frac{1}{\sqrt2}\\-\frac{1}{\sqrt2}\end{bmatrix} \begin{bmatrix}\frac{1}{\sqrt2}&-\frac{1}{\sqrt2}\end{bmatrix} = \begin{bmatrix}\frac{1}{2} & -\frac{1}{2}\\-\frac{1}{2} & \frac{1}{2}\end{bmatrix}$$Note that no information about a pure state is lost in this notation, because the vector $\mathbf{u}$ is uniquely determined, up to a scalar multiple, by the matrix $\mathbf{u}\mathbf{u}^\top$. 
There are several advantages to the density matrix notation. 
A mundane advantage is that we do not have to write so many square roots. 
More importantly, if $\mathbf{u}= \gamma\mathbf{v}$ for some [[Complex Numbers|complex]] scalar $\gamma$ with $|\gamma| = 1$, then $$\mathbf{u}\mathbf{u}^\top= \gamma\bar{\gamma}\mathbf{v}\mathbf{v}^\top = \mathbf{u}\mathbf{u}^\top$$Thus, the scalar factor disappears, and the normalized representation of each pure quantum state as a density matrix is unique.  
Also note that $tr(\mathbf{u}\mathbf{u}^\top) = ||\mathbf{u}||^2$. 
In particular, if $\mathbf{u}$ is a unit vector then the density matrix has [[Trace]] $=1$. 

The real strength of density matrices lies in the fact that they also provide a very economical notation for [[Pure and Mixed States|mixed states]]. 
A mixed state $\lambda_1\{u_1\}+\dots+\lambda_n\{u_n\}$ is simply represented as a linear combination of the density matrices of its pure components, i.e., as $\lambda_1\mathbf{u}_1\mathbf{u}_1^\top + \dots + \lambda_n\mathbf{u}_n\mathbf{u}_n^\top$. 
For example: the mixed state $\frac{1}{2}\{|0\rangle\}+\frac{1}{2}\{|1\rangle\}$ is expressed as the matrix $$\frac{1}{2} \begin{bmatrix}1 & 0\\0 & 0\end{bmatrix} + \frac{1}{2} \begin{bmatrix}0 & 0\\0 & 1\end{bmatrix} = \begin{bmatrix}\frac{1}{2} & 0\\0 & \frac{1}{2}\end{bmatrix}$$**Remark 3.4**
Some information about a mixed state is lost in the density matrix notation. 
For example, let $u = \frac{1}{\sqrt2}|0\rangle+ \frac{1}{\sqrt2}|1\rangle$ and $v = \frac{1}{\sqrt2}|0\rangle- \frac{1}{\sqrt2}|1\rangle$. 
Then the mixed state $\frac{1}{2}\{u\}+\frac{1}{2}\{v\}$ gives rise to the following density matrix $$\frac{1}{2}\begin{bmatrix}\frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2}\end{bmatrix} + \frac{1}{2}\begin{bmatrix}\frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2}\end{bmatrix} = \begin{bmatrix}\frac{1}{2} & 0 \\ 0 & \frac{1}{2}\end{bmatrix}$$which is the same as the density matrix for the mixed state $\frac{1}{2}\{|0\rangle\}+\frac{1}{2}\{|1\rangle\}$ calculated above. 
But, as we will see, there is no observable difference between two mixed states that share the same density matrix, and thus there is no harm (and indeed, much benefit) in identifying such states. 

We note that a matrix $A$ is of the form $\lambda_1\mathbf{u}_1\mathbf{u}_1^\top + \dots + \lambda_n\mathbf{u}_n\mathbf{u}_n^\top$ for unit vectors $\mathbf{u}_i$ and non-negative coefficient $\lambda_i$ with $\Sigma_i \lambda_i \leq 1$ if and only if $A$ is a [[Positive Operator#Positive Matrix|Positive Matrix]] and has [[Trace]] $\leq 1$ 
$A$ can be diagonalized as $A=SDS^\dagger$, for some $D=\Sigma_i\ \lambda_ie_ie_i^\top$. We then have that $A=\Sigma_i\ \lambda_iu_iu_i^\top$ where $u_i = Se_i$. 
This motivates the following definition:
>**Definition (Density Matrix):** A density matrix is a positive Hermitian matrix $A$ which satisfies $tr(A)\leq 1$.
   We write $D_n\subseteq\mathbb{C}^{n\times n}$ for the set of density matrices of dimension $n$

**Remark 3.5**
In any dimension a density matrix is a [[Pure Matrix]] iff its [[Rank of a Matrix|Rank]] is at most 1. 
More generally, any density matrix of rank $k$ can be decomposed into a sum of $k$ pure density matrices. 
In particular, since the addition of positive Hermitian matrices can only be rank-increasing, the sum of a pure and impure matrix is always impure. 

## Density Operator
This part is from [[Floyd-Hoare Logic for Quantum Programs]].

In quantum mechanics [[Mixed State]]s are described by **density matrices** or **density operators**, which are certain [[Trace-Class Operator]]. 

**A density matrix** (or **density operator**) **is a matrix that describes the quantum state of a physical system.** 
It allows for the calculation of the probabilities of the outcomes of any measurement performed upon this system. 

A **density operator** $\rho$ on a [[Hilbert Space]] $\mathcal{H}$ is defined to be a [[Positive Operator]] with [[Trace]] $tr(\rho) = 1$. 

Then a [[Mixed State]] of a quantum system with state space $\mathcal{H}$ is described by a density operator on $\mathcal{H}$. 

#### Partial Density Operator
We now see a slightly generalized notion of the density operator: a **partial density operator** $\rho$ is a [[Positive Operator]] with $tr(\rho) \leq 1$. 
In particular, the zero operator is a partial density operator. 

The set of partial density operators is denoted $\mathcal{D}^{-}(\mathcal{H})$. 

A partial density operator can also be defined by an ensemble of [[Pure State]]s. 
Suppose that a quantum system is in one of a number of pure states $|\psi_i\rangle$, with respective probabilities $p_i$, where is required that $\Sigma_i p_i \leq 1$. 
Then $\rho=\Sigma_ip_i|\psi_i\rangle\langle\psi_i|$ is a partial density operator. 

The notion of partial density operator allows us to follow **Selinger's normalization convention** "we normalize each state in such a way that the sum of the squares of the amplitudes is equal to the total probability that this state is reached". 

The partial density operator can be used to describe the global state of quantum variables because it provides a way to calculate the reduced density matrix of a subsystem, which is a key quantity in many quantum information protocols. 
By analyzing the partial density operators of the subsystems, one can gain insights into the properties of the global state, such as its entanglement structure and its potential for quantum information processing.
