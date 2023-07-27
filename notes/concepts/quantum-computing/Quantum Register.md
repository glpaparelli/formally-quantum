A **register** is a set of [[Qubit]]s treated as a composite system. 
In many quantum algorithms the qubits are divided into two registers: one for the main calculation from where the result comes out and the other for the draft (calculations that will be erased). 

Suppose we have a register with two qubits. The [[Computational Basis]] is $$|0,0\rangle= \begin{bmatrix}1\\0\\0\\0\end{bmatrix},\ |0,1\rangle = \begin{bmatrix}0\\1\\0\\0\end{bmatrix}, \ |1,0\rangle = \begin{bmatrix}0\\0\\1\\0\end{bmatrix}, \ |1,1\rangle= \begin{bmatrix}0\\0\\0\\1\end{bmatrix}$$
A generic state of this register is $$|\psi\rangle = \Sigma_{i=0}^1\Sigma_{j=0}^1\ a_{ij}|i,j\rangle$$where coefficients $a_{ij}$ are [[Complex Numbers]] that satisfy the constraint $$|a_{00}|^2 + |a_{10}|^2 + |a_{01}|^2 + |a_{11}|^2 = 1$$
To help generalizing to $n$ qubits it is usual to compress the notation by converting binary-base representation to decimal-base.
The computational basis for two-qubits register in decimal-base representation is $\{|0\rangle, |1\rangle, |2\rangle, |3\rangle\}$. 

In the binary-base representation we can determine the number of qubits counting the number of digits inside the ket, for example $|011\rangle$ refers to three qubits. 
This cannot be done if we use the decimal-base representation. 


