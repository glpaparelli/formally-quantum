A [[Linear Operator]] $\mathcal{U}$ (on a [[Hilbert Space]] $\mathcal{H}$) is called a **unitary operator**, represented as a matrix using the [[Matrix Representation]] and indicated with $U$ where $U$ is a unitary matrix, if $$U^\dagger U = I_\mathcal{H}$$where $I_\mathcal{H}$ is the identity operator on $\mathcal{H}$ and $U^\dagger$ is the [[Adjoint]] of $U$

## Unitary Matrix
This part is from [[Towards a Quantum Programming Language]]. 

A square matrix $S \in \mathbb{C}^{n\times n}$ is called **unitary** if $S^\dagger S = I$ where $I$ is the identity matrix, or equivalently if the [[Adjoint]] of $S$, represented with $S^\dagger$, is $S^{-1}$ (the [[Invertible Matrix|inversve matrix]])

Unitary matrices are precisely [[Isometry|isometries]], because the "[[Norm]] equation"$||S\mathbf{u}|| = ||\mathbf{u}||$ holds for every $\mathbf{u}$ if and only if $S$ is unitary.

If $S$ is a unitary matrix and $A = SBS^\dagger$, then $tr(A) = tr(B)$. 
Thus, the [[Trace]] is invariant under the unitary [[Change of Basis]].


