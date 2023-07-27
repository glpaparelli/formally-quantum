A [[Linear Operator]] $\mathcal{M}$ on an [[Hilbert Space]] $\mathcal{H}$ is said to be **Hermitian** if $$M^\dagger = M$$where $M^\dagger$ is the [[Adjoint]] of $M$ and $M$ is the [[Matrix Representation]] of $\mathcal{M}$

### Hermitian Matrix
This part is from [[Towards a Quantum Programming Language]]. 

Note that if the matrix $M$ is Hermitian then $\mathbf{u}^\top M \mathbf{u}$ is always a real number. 
Note that Hermitian matrices are closed under addition and real scalar multiples, i.e., they form a $\mathbb{R}$-linear subspace of $\mathbb{C}^{n\times n}$.

A matrix $A$ is Hermitian if and only if $A= SDS^\dagger$, for some [[Unitary Operator|Unitary Matrix]] $S$ and some real-valued diagonal matrix $D$. 
The diagonal entries of $D$ are the [[Eigenvalues and Eigenvectors|eigenvalues]] of $A$ and they are uniquely determined up to permutation. 
The columns of $S$ are the corresponding [[Eigenvalues and Eigenvectors|eigenvectors]]. 

A Hermitian matrix $A$ is a [[Positive Operator|Positive Matrix]] if and only if all its eigenvalues are non-negative. 

In dimension $2$, a matrix $$\begin{bmatrix}a & b \\ c & d\end{bmatrix}$$is Hermitian when $b = \bar{c}$ and $a,d \in \mathbb{R}$. Furthermore, it is a positive matrix when the [[Trace]] $a+d$ and the [[Determinant]] $ad-bc$ are non-negative. 
If the determinant is zero then the matrix is a [[Pure Matrix]]. 

#### Remarks 2.1
Any complex $\mathbb{C}^{n\times n}$ matrix is a linear combination of four [[Positive Operator|positive]] Hermitian matrices.
**proof:** todo

