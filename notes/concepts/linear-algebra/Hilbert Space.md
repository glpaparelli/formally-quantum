We use the [[Dirac Notation]] to represent vectors.
This part is from [[Floyd-Hoare Logic for Quantum Programs]]. 

Let $\{|\psi_n\rangle\}$ be a sequence of vectors in a [[Complex Numbers]] [[Vector Space]] $\mathcal{H}$. 
If for any $\epsilon > 0$ there exists a positive integer $N$ such that $||\psi_m - \psi_n|| < \epsilon$ for all $m,n \geq N$, then $\{|\psi_n\rangle\}$ is called a **Cauchy sequence.**

If for any $\epsilon$ there exists a positive integer $N$ such that $||\psi_n - \psi|| < \epsilon$ for all $n \geq N$, then $|\psi\rangle$is called a **limit** of $\{|\psi_n\rangle\}$ and we write $|\psi\rangle = \text{lim}_{n\rightarrow\infty} |\psi_n\rangle$.

A family ${|\psi_i\rangle}_{i\in I}$ of vectors in $\mathcal{H}$ is said to be **summable** with sum $|\psi\rangle$, and we write $|\psi\rangle = \Sigma_{i\in I}|\psi\rangle$ if for any $\epsilon$ there is a finite subset $J$ of $I$ such that $$||\psi - \Sigma_{i\in K}\psi_i|| < \epsilon$$ for every finite subset $K$ of $I$ containing $J$. 

Given an [[Orthonormal Basis]] $\{\psi_i\}_{i\in I}$. The cardinality of $I$ is called the **dimension** of $\mathcal{H}$.

**A Hilbert Space is defined as a complete inner product space; that is an inner product space in which each Cauchy sequence of vectors has a limit.** 

According to the [[1st Postulate - State Space]], the state space of an isolated quantum system is represented by a Hilbert space, and a [[Pure and Mixed States|pure state]] of the system is described by a unit vector (up to phase shift) in its state space (more on that later)

If $S$ is a subset of a Hilbert space $\mathcal{H}$, the set of vectors orthogonal to $S$ is defined by
$$S^\bot = \{\mathbf{x} \in \mathcal{H} : (\mathbf{x}, \mathbf{s}) = 0\ \forall  \mathbf{s} \in S\}$$
The set $S^\bot$ is a closed subspace of $\mathcal{H}$ and so forms itself a Hilbert space. 

If $V$ is a closed subspace of $\mathcal{H}$, then $V^\bot$ is called the **orthogonal complement** of $V$. 
In fact, every $\mathbf{x} \in \mathcal{H}$ can be written uniquely as $\mathbf{x} = \mathbf{v}+\mathbf{w}$, with $\mathbf{v} \in V$ and $\mathbf{w} \in V^\bot$. 
Therefore $\mathcal{H}$ is the internal Hilbert direct sum of $V$ and $V^\bot$ 

An N-dimensional Hilbert space will be denoted by $\mathcal{H}^n$. 
A Hilbert space associated with a system $A$ will be denoted by $\mathcal{H}_A$  


## Linear Operators on Hilbert Space
A [[Linear Transformation]] on a Hilbert Space $\mathcal{H}$ is a mapping $\mathcal{A}:\mathcal{H}\rightarrow\mathcal{H}$ that satisfy the following conditions: 
- $\mathcal{A}(|\psi\rangle + |\varphi\rangle)=\mathcal{A}|\psi\rangle + \mathcal{A}|\varphi\rangle$ 
- $\mathcal{A}(\lambda|\psi\rangle)= \lambda\mathcal{A}(|\psi\rangle)$ 
for all $|\varphi\rangle, |\psi\rangle \in \mathcal{H}$ and $\lambda \in \mathbb{C}$. 

If $\{\psi_i\}$ is an [[Orthonormal Basis]] of $\mathcal{H}$, then an operator $\mathcal{A}$ is uniquely determined by the images of $\{\mathcal{A}|\psi_i\rangle\}$ of basis vector $\{\psi_i\}$ under $\mathcal{A}$. 
In particular $\mathcal{A}$ can be represented by a matrix using the [[Matrix Representation]] of $\mathcal{A}$ $$A = (\langle\psi_i|\mathcal{A}|\psi_j\rangle)_{ij}$$when $\mathcal{H}$ is finite-dimensional. 
**notation reminder:** $\mathcal{A}|\psi_j\rangle$ is the vector obtained by applying $|\psi_j\rangle$ to $\mathcal{A}$. With this vector we do the inner product with $\psi_i$ and obtain the $ij$-th entry of the operator $\mathcal{A}$ represented as a matrix.

An operator $\mathcal{A}$ on $\mathcal{H}$ is said to be **bounded** if there is a constant $C>0$ such that $||A|\psi\rangle|| \leq C||\psi||$ for all $|\psi\rangle \in \mathcal{H}$.

We write $\mathcal{L}(\mathcal{H})$ for the set of bounded operators on $\mathcal{H}$.
The identity operator on $\mathcal{H}$ is denoted $I_\mathcal{H}$; that is $I_\mathcal{H}|\psi\rangle = |\psi\rangle$ for all $|\psi\rangle \in \mathcal{H}$. 
The zero operator on $\mathcal{H}$ that maps every vector in $\mathcal{H}$ to the zero vector is denoted $0_\mathcal{H}$