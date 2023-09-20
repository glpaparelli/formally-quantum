We use the Complex Numbers as a Field in the Vector Space, but the following is true also for other fields.

The **inner product** in the [[Complex Numbers]] field $\mathbb{C}$ is a binary operation $(.,.): V \times V \rightarrow \mathbb{C}$.

The inner product in a complex vector space satisfies several properties, including **linearity**, **conjugate symmetry**, and **positive-definiteness**. 
These properties allow for the definition of geometric notions such as lengths, angles, and orthogonality of vectors.

The **linearity property** of the inner product states that for any vectors $\mathbf x$, $\mathbf y$, and $\mathbf z$ in the complex vector space and any complex scalars $a$ and $b$, the inner product satisfies the following:
- **linearity in the first argument:**  $(a\mathbf x + b\mathbf y, \mathbf z) = a(\mathbf x, \mathbf z) + b(\mathbf y, \mathbf z)$ 
- **linearity in the second argument:** $(\mathbf x, a\mathbf z + b\mathbf w) = a(\mathbf x, \mathbf z) + b(\mathbf x, \mathbf w)$ 

The **conjugate symmetry property** of the inner product states that for any vectors $\mathbf x$ and $\mathbf y$ in the complex vector space, the inner product satisfies the following:
- **conjugate symmetry:** $(\mathbf x,\mathbf  y) = (\mathbf y,\mathbf x)^*$ 
 
The **positive-definiteness property** of the inner product states that for any vector $\mathbf x$ in the complex vector space, the inner product satisfies the following:
- Positive-definiteness: $(\mathbf x, \mathbf x)\geq0$, with equality if and only if $x = 0$

These properties ensure that the inner product captures the geometric properties of vectors in the complex vector space, such as the notion of length, angle, and orthogonality.

There is more than one way to define an inner product on a [[Vector Space]]. 
In the [[Complex Numbers]] [[Vector Space]] $\mathbb{C}^n$ the most used inner product is defined as follows: 
Given two vectors $\mathbf{v}, \mathbf{w}$ $$ \mathbf{v} = \begin{bmatrix} a_1 \\ . \\ . \\ . \\ a_n \end{bmatrix} , \ \ \mathbf{w} = \begin{bmatrix} b_1 \\ . \\ . \\ . \\ b_n \end{bmatrix}$$We define their inner product as:
$$(\mathbf{v}, \mathbf{w}) = \Sigma_{i=1}^n \ a^*_ib_i$$
Where $a_i^*$ is the complex conjugate of $a_i$. 
This expression is equivalent to the matrix product of the transpose-conjugate vector, which is usually denoted by $\mathbf{v}^\dagger$, by $\mathbf{w}$. 

Notice this important property: $$(\mathbf{u}, \mathbf{u}) = \Sigma_i|u_i|^2\geq0$$said easy: the inner product of a vector with itself is always $\geq$ 0.

The [[Dot Product]] is a special case of the Inner Product.
