**The Dirac notation is yet another notation used for vectors.** 
The Dirac notation (or bra-ket notation) uses $\mathbf{v} \equiv |v\rangle$ 

From this point on, instead of using bold to represent vector, we put the letter $v$ between a vertical bar and a right angle bracket. 
If we have an indexed basis $\{\mathbf{v}_1, ..., \mathbf{v}_n\}$ then we write, using the Dirac notation, $\{|v_1\rangle,...,|v_n\rangle\}$ 

Computer scientists usually starts counting from $0$, so the first basis vector is usually called $\mathbf{v}_0$. 
In the Dirac notation we have $\mathbf{v}_0 \equiv |0\rangle$. 
Notice that the vector $|0\rangle$ is not the zero vector, it is only the first vector in a collection of vectors. 
In the Dirac notation the zero vector is an exception, whose notation is not modified, and we represent it with $\mathbf{0}$.

Suppose the vector $|v\rangle$ has the following entries in a basis: 
$$
|v\rangle = \begin{bmatrix} a_1 \\. \\ . \\ . \\ a_n \end{bmatrix}
$$
Its dual vector is denoted by $\langle v |$ and is defined by: 
$$
\langle v | = [a_1^* \ ... \ a_n^*] 
$$
As usual vectors and their duals can be seen as column and row matrices, respectively, for algebraic manipulation.
The matrix product of $\langle v |$ by $| v \rangle$ is denoted by $\langle v | v \rangle$  and its value in terms of their entries is: 
$$
\langle v | v \rangle = \Sigma_{i=1}^n \ a_i^* a_i
$$
**This is an example of the [[Inner Product]], which is naturally defined via the Dirac notation.** 


The [[Norm]] of a vector in this notation is $|| |v\rangle || = \sqrt{\langle v | v \rangle}$. 

We use the terminology **ket** for vector $|v\rangle$ and **bra** for dual vector $\langle v |$. 
Keeping consistency, we use the terminology **bra-ket** for $\langle v | v \rangle$. 

The key to the Dirac notation is to always view kets $|.\rangle$ as column matrices, bras $\langle .|$ as row matrixes and recognize that a sequence of bras and kets is a matrix product, hence associative, but not-commutative. 

It is also very common to meet the matrix product of $|v\rangle$ by $\langle v|$, denoted by $|v\rangle \langle v|$, known as the [[Outer Product]],
