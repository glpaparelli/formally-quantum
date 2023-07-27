We use the [[Dirac Notation]] to represent vectors.

[[Linear Operator]]s can be represented by matrices. 
Let $\mathcal{A}:V\rightarrow W$ be a linear operator and let $\{|v_1\rangle,\ \dots,\ |v_n\rangle\}$ and $\{|w_1\rangle,\ \dots,\ |w_n\rangle\}$ be orthonormal bases for $V$ and $W$ respectively. 

A **matrix representation** of $\mathcal{A}$ is obtained by applying $\mathcal{A}$ to every vector in the basis of $V$ and expressing the result as a linear combination of basis vectors of $W$, as follows:$$\mathcal{A}(|v_j\rangle) = \Sigma_{i=1}^n\ a_{ij}|w_j\rangle$$where the index $j$ runs from $1$ to $n$. 

The $a_{ij}$ are the entries of a $m\times n$ matrix, which we call $A$. 
The expression $\mathcal{A}(|v_j\rangle)$ is equivalent to the matrix product $A|v_j\rangle$. 

Using the [[Outer Product]] notation, we have:$$A = \Sigma_{i=1}^m\Sigma_{j=1}^n\ a_{ij}|w_i\rangle\langle v_j|$$
