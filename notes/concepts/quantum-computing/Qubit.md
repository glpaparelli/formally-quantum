We use the [[Dirac Notation]] to represent vectors.

Conventional computers are made up of bits, quantum computers are made up of **quantum bits** or **qubits**.
The bit is the fundamental concept of classical computation. 
We can think of the bit in abstract terms, as having a state which is either $0$ or $1$.

**A qubit is the simplest of all quantum systems**
- just like a bit, a qubit has a state
- two special states for a qubit are the states $|0\rangle$ and $|1\rangle$, which corresponds to the states $0$ and $1$ for a classical bit$$|0\rangle = \begin{bmatrix} 1 \\ 0\end{bmatrix} , \ \ |1\rangle = \begin{bmatrix} 0 \\ 1\end{bmatrix}$$The basis states $|0\rangle = 1|0\rangle + 0|1\rangle$ and $|1\rangle = 0|0\rangle + 1|1\rangle$ are called **classical states**, and any other state is said to be a quantum [[Quantum Mechanics Phenomenas#Superposition|superposition]] of $|0\rangle$ and $|1\rangle$ 
- the difference between bits and qubits is that a **qubit can be in a state other than $|0\rangle$ or $|1\rangle$: a qubit can be in a** [[Quantum Mechanics Phenomenas#Superposition|superposition]] of the two states simultaneously $$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$
- the representation of information is binary but each qubit contains double information respect to a bit

**Similarly said:**
The qubit is a **unit vector** in the [[Complex Numbers]] [[Vector Space]] $\mathbb{C}^2$. A generic qubit $|\psi\rangle$ is represented as $$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$where the coefficients $\alpha$ and $\beta$, which are called **amplitudes of the state** $|\psi\rangle$, are complex numbers and obey the constraint $$|\alpha|^2 + |\beta|^2 = 1$$and they are only significant up to scalar multiplies, i.e., $q = \alpha|0\rangle + \beta|1\rangle$ and $q' = \alpha'|0\rangle + \beta'|1\rangle$ denote **the same quantum state** if $\alpha'= \gamma\alpha$ and $\beta'= \gamma\beta$ for some non-zero $\gamma \in \mathbb{C}$. 

The term **state** (or state vector) is used as a synonym for **unit vector in a** [[Hilbert Space]]. A unit vector is a vector with [[Norm]] $=1$. 
The state of a single qubit can be described by a **linear combination** of the state $|0\rangle$ and $|1\rangle$
$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle = \alpha\begin{bmatrix} 1 \\ 0\end{bmatrix} + \beta \begin{bmatrix} 0 \\ 1\end{bmatrix} = \begin{bmatrix} \alpha \\ \beta\end{bmatrix}, \ \ \ \alpha,\beta \in \mathbb{C}$$
The special states $|0\rangle$ and $|1\rangle$ are known as [[Computational Basis]] states, and form an [[Orthonormal Basis]] for this **vector space** ($\mathbb{C}^2$) 

We can examine a bit to determine whether it is in state $0$ or $1$, but we **cannot examine a qubit** to determine its quantum state (the values of $\alpha$ and $\beta$).
We can only acquire much more restricted information about the quantum state. 

Measuring a qubit can only give classical results
- either the result is $0$, with probability $|\alpha|^2$
- or the result is $1$, with probability $|\beta|^2$

We can have the following **taxonomy:**
- **deterministic bit:** the state of classical bit can be described by a single binary value, which can be equal to either $0$ or $1$. The state can be represented as one of two points, labelled '0' and '1'
- **probabilistic classical bit:** the state of a probabilistic bit is described by the probabilities $p_0$ and $p_1$ (real and non-negative), which satisfy $p_0 + p_1 = 1$. The state of a bit can be drawn as a point on the line between the positions $0$ and $1$
- **quantum bit:** a qubit $|\psi\rangle$ can be represented in a three-dimensional space, as a point on the surface of a sphere or unitary radius known as the [[Bloch Sphere]]

![[bits.png | center | 600]]

**Normalization Constraint**
The condition that the state vector is a unit vector means that $$\langle\psi|\psi\rangle =|a^2| + |b^2| = 1$$and express the idea that the probabilities for the outcomes of a computational basis measurement add up to 1.

**How much information is represented by a qubit?**
$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$
- $\alpha$ is a complex number, and we could imagine storing lots of classical bits in the binary expansion of the real component of $\alpha$
- if there was some experimental way you could measure the value of $\alpha$ exactly, then you could extract that classical information
- however $\alpha$ and $\beta$ are kind of hidden information
	- measurement of a qubit will give only a single bit of information, either $0$ or $1$, about the state of the qubit
	- there is now way to figure out $\alpha$ and $\beta$ if they start out unknown: after the measurement $\alpha$ and $\beta$ are gone
	- why does this type of collapse occur? nobody knows 

A qubit can be in a superposition of $2$ states, the state of $n$ qubit can be in a superposition of $2^n$ states. 
Performing operations on $n$ qubits is as operating on $2^n$ bits of information at the same time. 
The idea is to find an algorithm that makes all $2^n$ states of the qubits converge in one that is the solution of a problem under consideration.
This by exploiting constructive or destructive interference: positive and negative amplitudes may cancel or reinforce. 

### QPL: Quantum Bits
This part is from [[Towards a Quantum Programming Language]].
An interesting fact about quantum bits is that the states of two or more qubits is not just a tuple of its components. 
The four possible states of a pair of classical bits are $00, 01, 10, 11$. 
The state of a pair of quantum bits is a formal complex linear combination of these four classical states, i.e., it is a linear combination of the form $$\alpha_{00}|00\rangle + \alpha_{01}|01\rangle + \alpha_{10}|10\rangle + \alpha_{11}|11\rangle = \Sigma_{i,j \in \{0,1\}}\alpha_{ij}|ij\rangle$$As before we require that at least one of the $\alpha_{ij}$ is non-zero and the whole state is only well-defined up to complex scalar multiple. 
If $q = \alpha|0\rangle + \beta|1\rangle$ and $p = \gamma|0\rangle + \delta|1\rangle$ are two independent quantum bits, then their combined state is obtained through the [[Tensor Product]], using the [[4th Postulate - Composition of Systems]]: 
$$q \bigotimes p=\alpha\gamma|00\rangle+\alpha\beta|01\rangle+\beta\gamma|10\rangle+\beta\gamma|11\rangle$$
However, note that in general, the state space of a pair of quantum bits needs not to be of the form $q \bigotimes p$. 
For instance, the state $$\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|11\rangle$$ is not in the form $q \bigotimes p$. 
If the state of a pair of quantum bits is in the form $q \bigotimes p$ then the pair is said to be **independent**, otherwise it is called **entangled**. 

In general, the state of $n$ quantum bits is a non-zero vector in $\mathbb{C}^{2^n}$, i.e., a formal linear combination $$\Sigma_{b_1,\ \dots,\ b_n \in \{0,1\}}\alpha_{b_1,\ \dots,\ b_n}|b_1,\ \dots,\ b_n\rangle$$taken modulo scalars multiples. 

##### Indexing Conventions
Consider the quantum state $q = \alpha|00\rangle + \beta|01\rangle + \gamma|10\rangle + \delta|11\rangle$. 
By identifying the basis vectors $|00\rangle, |01\rangle, |10\rangle, |11\rangle$ with the [[Computational Basis]] of $\mathbb{C}^4$, we can write the state $q$ as the column vector $$|q\rangle = \begin{bmatrix}\alpha\\\beta\\\gamma\\\delta\end{bmatrix}$$**Here the ordering of the basis vectors is relevant.** 
In general we need an indexing convention which determines how the basis vectors  $|b_1\dots b_n\rangle$ are to be identified with the canonical basis vectors of $\mathbb{C}^{2^n}$.

###### Convention 3.1
> **Lexicographic Convention**
	Consider the set of bit vectors of length $n$, i.e., tuples $(b_1, b_2,\ \dots,\ b_n)$, where each $b_i \in \{0,1\}$.
	We identify each such bit vector with the number $i \in [0, 2^{n-1}]$ of which it is the binary representation (there are $2^n$ possible bit vectors, every possible combination of $0$ and $1$). 
	We also identify the "ket" $|b_1b_2\dots b_n\rangle$ with the $i-th$ canonical basis vector of $\mathbb{C}^{2^n}$ 

Note that this convention is equivalent to saying that the bit vectors shall always be ordered lexicographically when they are used to index the rows or the columns of some vector or matrix. 

Sometimes we need to consider a permutation of quantum bits, such as exchanging the 1st and the 2nd qubit in a sequence. 
This induces a corresponding permutation of states. 
More precisely, any permutation of $n$ elements $\phi:\{1,\ \dots,\ n\}\rightarrow \{1,\ \dots,\ n\}$ induces a permutation $2^\phi$ of the set of bit vectors of length $n$, which is defined by $2^\phi(x_1,\ \dots,\ x_n) = (x_{\phi^{-1}(1)},\ \dots,\ x_{\phi^{-1}(n)})$, for $x_1,\ \dots,\ x_n \in \{0, 1\}$. 
Note that this definition is **covariant**, in sense that $2^\phi \circ 2^\psi = 2^{\phi\circ\psi}$. 
As an illustration, consider the permutation $\phi$ such that $\phi(1) = 2,\ \phi(2) = 3,\ \phi(3) = 1$. 
Then $2^\phi(b_1,b_2,b_3) = (b_3, b_1, b_2)$, thus $2^\phi$ maps $000\rightarrow 000,\ 100\rightarrow 010,\ 110\rightarrow 011$ and so forth 