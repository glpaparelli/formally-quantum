We use the [[Dirac Notation]] to represent vectors.

Conventional computers are made up of bits, quantum computers are made up of **quantum bits** or **qubits**.
The bit is the fundamental concept of classical computation. 
We can think of the bit in abstract terms, as having a state which is either $0$ or $1$.

**A qubit is the simplest of all quantum systems**
- just like a bit, a qubit has a state
- two special states for a qubit are the states $|0\rangle$ and $|1\rangle$, which corresponds to the states $0$ and $1$ for a classical bit$$|0\rangle = \begin{bmatrix} 1 \\ 0\end{bmatrix} , \ \ |1\rangle = \begin{bmatrix} 0 \\ 1\end{bmatrix}$$The basis states $|0\rangle = 1|0\rangle + 0|1\rangle$ and $|1\rangle = 0|0\rangle + 1|1\rangle$ are called **classical states**, and any other state is said to be a quantum [[Quantum Mechanics Phenomenas#Superposition|superposition]] of $|0\rangle$ and $|1\rangle$ 
- the difference between bits and qubits is that a **qubit can be in a state other than $|0\rangle$ or $|1\rangle$: a qubit can be in a** [[Quantum Mechanics Phenomenas#Superposition|superposition]] of the two states simultaneously $$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$
## Formal Definition of a Qubit
The qubit is a **unit vector** in the [[Complex Numbers]] [[Vector Space]] $\mathbb{C}^2$. 
A generic qubit $|\psi\rangle$ is represented as $$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$where the coefficients $\alpha$ and $\beta$, which are called **amplitudes of the state** $|\psi\rangle$, and are complex numbers and obey the **normalization constraint**, that express how $\alpha$ and $\beta$ are "complex probabilities"$$|\alpha|^2 + |\beta|^2 = 1$$
**The amplitudes are only significant up to scalar multiplies**, i.e., $q = \alpha|0\rangle + \beta|1\rangle$ and $q' = \alpha'|0\rangle + \beta'|1\rangle$ denote **the same quantum state** if $\alpha'= \gamma\alpha$ and $\beta'= \gamma\beta$ for some non-zero $\gamma \in \mathbb{C}$. 

The term **state** (or state vector) is used as a synonym for **unit vector in a** [[Hilbert Space]]. 
A **unit vector** is a vector with [[Norm]] $=1$. 
The state of a single qubit can be described by a **linear combination** of the state $|0\rangle$ and $|1\rangle$
$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle = \alpha\begin{bmatrix} 1 \\ 0\end{bmatrix} + \beta \begin{bmatrix} 0 \\ 1\end{bmatrix} = \begin{bmatrix} \alpha \\ \beta\end{bmatrix}, \ \ \ \alpha,\beta \in \mathbb{C}$$
The special states $|0\rangle$ and $|1\rangle$ are known as [[Computational Basis]] states, and form an [[Orthogonal-Orthonormal Basis|Orthonormal Basis]] for this **vector space** ($\mathbb{C}^2$).
The vector $\begin{bmatrix} \alpha \\ \beta\end{bmatrix}$ is, as always, called **coordinate vector**. 

We can examine a bit to determine whether it is in state $0$ or $1$, but we **cannot examine a qubit** to determine its quantum state (the values of $\alpha$ and $\beta$).
We can only acquire much more restricted information about the quantum state. 

**Measuring a qubit can only give classical results**
- either the result is $0$, with probability $|\alpha|^2$
- or the result is $1$, with probability $|\beta|^2$

We can have the following **taxonomy:**
- **deterministic bit:** the state of classical bit can be described by a single binary value, which can be equal to either $0$ or $1$. The state can be represented as one of two points, labelled '0' and '1'
- **probabilistic classical bit:** the state of a probabilistic bit is described by the probabilities $p_0$ and $p_1$ (real and non-negative), which satisfy $p_0 + p_1 = 1$. The state of a bit can be drawn as a point on the line between the positions $0$ and $1$
- **quantum bit:** a qubit $|\psi\rangle$ can be represented in a three-dimensional space, as a point on the surface of a sphere or unitary radius known as the [[Bloch Sphere]]

![[bits.png | center | 600]]

### How Much Information there is in a Qubit?
$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$
- $\alpha$ is a complex number, and we could imagine storing lots of classical bits in the binary expansion of the real component of $\alpha$
- if there was some experimental way you could measure the value of $\alpha$ exactly, then you could extract that classical information
- however $\alpha$ and $\beta$ are hidden information
	- measurement of a qubit will give only a single bit of information, either $0$ or $1$, about the state of the qubit
	- there is now way to figure out $\alpha$ and $\beta$ if they start out unknown: after the measurement $\alpha$ and $\beta$ are gone
	- why does this type of collapse occur? nobody knows 

A qubit can be in a superposition of $2$ states, the state of $n$ qubit can be in a superposition of $2^n$ states. 
**Performing operations on $n$ qubits is as operating on $2^n$ bits of information at the same time.** 
The idea is to find an algorithm that makes all $2^n$ states of the qubits converge in one that is the solution of a problem under consideration.
This by exploiting constructive or destructive interference: positive and negative amplitudes may cancel or reinforce. 