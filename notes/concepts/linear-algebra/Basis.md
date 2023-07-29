A **basis** of a [[Vector Space]] $V$ is a **minimal collection** of vectors $\mathbf{v}_1, \dots, \mathbf{v}_n$ such that every other vector $\mathbf{v} \in V$ can be expressed as a linear combination of these: 
$$\mathbf{v} = \alpha_1\mathbf{v}_1 + \dots + \alpha_n\mathbf{v}_n$$
Where $n$ is the size of the basis and it is uniquely determined by $V$ and it is called **dimension of of the vector space.**

Given a vector space $V$ of size $n$ its basis consists in exactly $n$ **linearly independent** vectors. 
Two or more vectors are said to be **linearly independent** if none of them can be written as a linear combination of the others.

**Given a basis every vector can be represented as an $n-$tuple of scalars.**
You fix a basis and the $n-$tuple of scalars is the column vector where its entries are the coefficient of the linear combination of the vector you are representing: consider the basis $\{\mathbf{v}_1, \dots, \mathbf{v}_n\}$ and the vector $\mathbf{u}$ which can be expressed as the linear combination $\mathbf{u} = \alpha_1\mathbf{v}_1 + \dots + \alpha_n\mathbf{v}_n$, the vector $\mathbf{u}$ can be represented as $$ \begin{bmatrix}\alpha_1\\\alpha_2\\.\\.\\\alpha_n\end{bmatrix}$$This vector is often called the **coordinate vector**.
Mind that this representation is basis-dependent: if we use another basis we will have another vector. 
However we can convert between these representations using a change of basis matrix. 

If $\{\mathbf{v_1}, ..., \mathbf{v_n}\}$ is a basis for $\mathbb{C}^n$, then a generic vector $\mathbf{v}\in\mathbb{C}^n$ can be written as
$$
\mathbf{v} = \Sigma_{i=1}^{n} a_i\mathbf{v_i}
$$
where coefficients $a_i$ are [[Complex Numbers]]. 