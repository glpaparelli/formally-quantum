We use the [[Dirac Notation]] to represent vectors.

The state space of a composite physical system is the [[Tensor Product]] of the state spaces of the component subsystems. 
Moreover, if we have systems numbered $1$ through $n$, and system numbered $i$ is prepared in the state $|\psi_i\rangle$, the the joint state of the total system is $$|\psi_1\rangle \bigotimes |\psi_2\rangle \bigotimes \dots |\psi_n\rangle$$**notes:**
- we often omit the $\bigotimes$ symbol and write the joint state like $|\psi_1\rangle |\psi_2\rangle \dots |\psi_n\rangle$, or sometimes even as $|\psi_1,\ \psi_2,\ \dots,\ \psi_n\rangle$ or $|\psi_1 \psi_2 \ \dots \ \psi_n\rangle$
- why is the tensor product the mathematical structure used to describe the state space of a composite physical system? **Intuition:** we need a new space which captures the interaction of all $n$ subsystems
- **not all states of a combined system can be separated into the tensor product of states of the individual components**

#### Joint States of Two Qubits
Given two [[Qubit]]s $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle = \begin{bmatrix} \alpha \\ \beta\end{bmatrix}$ and $|\varphi\rangle = \gamma|0\rangle + \delta|1\rangle = \begin{bmatrix} \gamma \\ \delta\end{bmatrix}$  we define the **joint state of the two qubits** as 
$$
|\psi\rangle \bigotimes |\varphi\rangle = \begin{bmatrix} \alpha \\ \beta\end{bmatrix} \bigotimes \begin{bmatrix} \gamma \\ \delta\end{bmatrix} = \begin{bmatrix} \alpha\gamma \\ \alpha\delta \\ \beta\gamma \\ \beta\gamma\end{bmatrix} = \alpha\gamma|00\rangle + \alpha\delta|01\rangle+\beta\gamma|10\rangle+\beta\gamma|11\rangle
$$
using the **standard basis notation**:
$$|00\rangle = \begin{bmatrix} 1 \\ 0 \\ 0 \\ 0\end{bmatrix}, \ \ |01\rangle = \begin{bmatrix} 0 \\ 1 \\ 0 \\ 0\end{bmatrix}, \ \ |10\rangle = \begin{bmatrix} 0 \\ 0 \\ 1\\ 0\end{bmatrix}, \ \ |11\rangle = \begin{bmatrix} 0 \\ 0 \\ 0 \\ 1\end{bmatrix}$$
#### Separable States
A state $|\psi\rangle \in \mathbb{C}^n \bigotimes \mathbb{C}^n$ of a combined system is a **separable state** if it can be expressed as $\psi\rangle = |\psi_1\rangle \bigotimes |\psi_2\rangle$ for some $|\psi_1\rangle \in \mathbb{C}^2$ and $|\psi_2\rangle \in \mathbb{C}^2$ 

**Example:**
This two-qubit state is a separable state: 
$$\frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle) = \frac{1}{\sqrt2}(|0\rangle + |1\rangle)\bigotimes \frac{1}{\sqrt2}(|0\rangle + |1\rangle)$$
**Note:** if the two qubits are prepared independently, and kept isolated, then each qubit forms a closed system, and the state **can** be written in he product form. 

### Entangled States
The two-qubit state $$|\psi\rangle = \frac{1}{\sqrt2}(|00\rangle + |11\rangle) = \frac{1}{\sqrt2}\begin{bmatrix} 1 \\ 0 \\ 0 \\ 1\end{bmatrix}$$**cannot** be written as a product of single-qubit states, hence it is **entangled**.
Indeed, there are no single qubit states $\psi_1 = \alpha|0\rangle + \beta|1\rangle$ and $\psi_2 = \gamma|0\rangle + \delta|1\rangle$ such that $|\psi\rangle = |\psi_1\rangle + |\psi_2\rangle$.

For all $\alpha_0, \alpha_1, \beta_0, \beta_1 \in \mathbb{C}$
$$|\psi_1\rangle \bigotimes |\psi_2\rangle = \begin{bmatrix} \alpha \\ \beta\end{bmatrix} \bigotimes \begin{bmatrix} \gamma \\ \delta\end{bmatrix} = \begin{bmatrix} \alpha\gamma \\ \alpha\delta \\ \beta\gamma \\ \beta\gamma\end{bmatrix} \neq \frac{1}{\sqrt2}\begin{bmatrix} 1 \\ 0 \\ 0 \\ 1\end{bmatrix}$$

**Alternatively Said:**
This part is from [[Towards a Quantum Programming Language]].
An interesting fact about [[Qubit]]s is that the states of two or more qubits is not just a tuple of its components. 
The four possible states of a pair of classical bits are $00, 01, 10, 11$. 
The state of a pair of quantum bits is a formal complex linear combination of these four classical states, i.e., it is a linear combination of the form $$\alpha_{00}|00\rangle + \alpha_{01}|01\rangle + \alpha_{10}|10\rangle + \alpha_{11}|11\rangle = \Sigma_{i,j \in \{0,1\}}\alpha_{ij}|ij\rangle$$As before we require that at least one of the $\alpha_{ij}$ is non-zero and the whole state is only well-defined up to complex scalar multiple. 
If $q = \alpha|0\rangle + \beta|1\rangle$ and $p = \gamma|0\rangle + \delta|1\rangle$ are two independent quantum bits, then their combined state is obtained through the [[Tensor Product]], using the [[4th Postulate - Composition of Systems]]: 
$$q \bigotimes p=\alpha\gamma|00\rangle+\alpha\beta|01\rangle+\beta\gamma|10\rangle+\beta\gamma|11\rangle$$
However, note that in general, the state space of a pair of quantum bits needs not to be of the form $q \bigotimes p$
For instance, the state $$\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|11\rangle$$is not in the form $q \bigotimes p$. 
If the state of a pair of quantum bits is in the form $q \bigotimes p$ then the pair is said to be **independent**, otherwise it is called **entangled**.
To understand why this state is entangled, we can look at the probabilities of measuring the individual qubits in the state $|0\rangle$ or $|1\rangle$. 
If the two qubits were independent, then the probability of measuring the first qubit in the state $|0\rangle$ would be $\frac{1}{\sqrt2}$ and the probability of measuring the second qubit in the state $|0\rangle$ would also be $\frac{1}{\sqrt2}$. However, in the entangled state $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|11\rangle$, the probability of measuring the first qubit in the state $|0\rangle$ is $\frac{1}{\sqrt2}$, but the probability of measuring the second qubit in the state $|0\rangle$ is also $\frac{1}{\sqrt2}$. 
**This means that the two qubits are correlated in a way that cannot be explained by independent states.**
In fact, the entangled state $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|11\rangle$ assumes that the pair is with probability 0 in the state $|10\rangle$ and with probability 0 in the state $|11\rangle$. 
This means that if we measure one qubit to be in the state $|0\rangle$, then we know with certainty that the other qubit is also in the state $|0\rangle$. 
Similarly, if we measure one qubit to be in the state $|1\rangle$, then we know with certainty that the other qubit is also in the state $|1\rangle$. This correlation between the two qubits is what makes the state entangled


In general, the state of $n$ quantum bits is a non-zero vector in $\mathbb{C}^{2^n}$, i.e., a formal linear combination $$\Sigma_{b_1,\ \dots,\ b_n \in \{0,1\}}\alpha_{b_1,\ \dots,\ b_n}|b_1,\ \dots,\ b_n\rangle$$taken modulo scalars multiples. 

### Composite Systems
Suppose we have a 2-qubit composite system $|\Psi_1\rangle \bigotimes |\Psi_2\rangle$ and we apply the NOT gate $X$ only to the first qubit
![[composite-system-1.png | center | 400]]
We implicitly apply the identity operator $I$ to the second qubit at the same time
![[composite-system-2.png | center | 400]]
$|\Psi_1\rangle \bigotimes |\Psi_2\rangle$ gets mapped to $X|\Psi_1\rangle \bigotimes I|\Psi_2\rangle = (X \bigotimes I)(|\Psi_1\rangle \bigotimes |\Psi_2\rangle)$

**For a n-qubit composite system** $|\Psi_1\rangle \bigotimes |\Psi_2\rangle \bigotimes \dots \bigotimes|\Psi_n\rangle$, applying the gate $X$ to the first qubit corresponds to applying the operation $X \bigotimes I \bigotimes \dots \bigotimes I$, with $I$ repeated $n-1$ times to the entire system. 
![[composite-system-3.png | center | 400]]

Just as there are 2-qubits states that cannot be written as the product of two 1-qubit states, there are 2-qubit gates (acting on both qubits) that cannot be written as a tensor product of two 1-qubit gates.

**Example:** Quantum controlled-not, or [[CNOT Gate]]
The CNOT gate flips the state of the second qubit if the first qubit is in state $|1\rangle$, and does nothing otherwise: 
$$|00\rangle \rightarrow |00\rangle,\ |01\rangle \rightarrow |01\rangle,\ |10\rangle \rightarrow |11\rangle,\ |11\rangle \rightarrow |10\rangle$$
The [[Matrix Representation]] **for the CNOT gate** is 
$$
\begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0  & 1 & 0\end{bmatrix}
$$
and it cannot be written as a tensor product of two 1-qubit gates.

#### Multiple Qubits: Measurement
Let us consider a 2-qubit state $|\Psi\rangle = \alpha|00\rangle + \beta|01\rangle + \gamma|10\rangle + \delta|11\rangle$. 
A complete set of measurement operators in the computational basis would be: 
- $P_{00} = |00\rangle\langle00|$
- $P_{01} = |01\rangle\langle01|$
- $P_{10} = |10\rangle\langle10|$
- $P_{11}=|11\rangle\langle11|$

When we measure the two qubits in the computational basis: 
- the probability of getting the result $00$ is $|\alpha|^2$
- the probability of getting the result $01$ is $|\beta|^2$
- the probability of getting the result $10$ is $|\gamma|^2$
- the probability of getting the result $11$ is $|\delta|^2$

**How do we measure only the first qubit?**
![[composite-system-4.png | center | 600]]
![[composite-system-5.png | center | 700]]
