This part is from [[Towards a Quantum Programming Language]]. 

The binary gate $X$ corresponds to an exchange of to [[Qubit]]s: it maps $|b_1b_2\rangle$ to $b_2b_1$, whenever $b_1,b_2 \in \{0,1\}$. 
$$X = \begin{bmatrix}1 & 0 & 0 & 0\\0&0&1&0\\0&1&0&0\\0&0&0&1\end{bmatrix}$$

The $X$ gate is classical in the sense that it can be implemented as an operation on addresses of qubits, rather than on qubit themselves. 