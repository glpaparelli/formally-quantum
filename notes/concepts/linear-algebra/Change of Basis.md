Change of [[Basis]] is a technique used in linear algebra to rewrite vectors in terms of a different set of basis elements.
It is useful for many types of matrix computations in linear algebra and can be viewed as a type of [[Linear Transformation]].

Suppose we have a [[Vector Space]] with two different bases, say $\mathcal{B}_1 = \{\mathbf{v}_1, \mathbf{v}_2,\ \dots,\ \mathbf{v}_n\}$ and $\mathcal{B}_2 = \{\mathbf{u}_1, \mathbf{u}_2,\ \dots,\ \mathbf{u}_n\}$. 
We can translate vectors in terms of one basis into terms of the other using a **change of basis matrix**

**The change of basis matrix is a matrix that converts the coordinates of a vector from one basis to another.**

To find the change of basis matrix from $\mathcal{B}_1$ to $\mathcal{B}_2$, we express each basis vector in $\mathcal{B}_1$ as a linear combination of the basis vectors in $\mathcal{B}_2$ and form a matrix whose columns are the **coordinate vectors** of the basis vectors in $\mathcal{B}_1$ with respect to $\mathcal{B}_2$.
This matrix is called the change of basis matrix from $\mathcal{B}_1$ to $\mathcal{B}_2$ 

If we have a linear transformation $T: V \to V$ with matrix $N$ in basis $\mathcal{B}_1$, and $V$ has another basis $\mathcal{B}_2$, then if $M$ is the change-of-basis matrix for $\mathcal{B}_1$ to $\mathcal{B}_2$, the linear transformation $T$ can be represented by the matrix $M^{-1}NM$ in basis $\mathcal{B}_2$, using the [[Matrix Representation]].