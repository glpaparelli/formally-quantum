When we use the [[Matrix Representation]] for [[Linear Transformation]]s, the [[Tensor Product]] can be calculated explicitly via the **Kronecker Product**. 

Let $A$ be a $m\times n$ matrix and let $B$ be a $p\times q$ matrix. 
Then: $$A \bigotimes B= \begin{bmatrix}a_{11}B & \dots & a_{1n}B \\ \dots & \dots & \dots \\ \dots & \dots & \dots \\ a_{m1}B & \dots & a_{mn}B\end{bmatrix}$$The dimension of the resulting matrix is $mp\times nq$. 

The Kronecker product can be used for matrices of any dimension, particularly for two vectors: 
$$\begin{bmatrix}a_1 \\ a_2\end{bmatrix} \bigotimes \begin{bmatrix}b_1 \\ b_2\end{bmatrix} = \begin{bmatrix}a_1\begin{bmatrix}b_1 \\ b_2\end{bmatrix} \\ a_2\begin{bmatrix}b_1 \\ b_2\end{bmatrix}\end{bmatrix} = \begin{bmatrix}a_1b_1 \\ a_1b_2 \\ a_2b_1 \\ a_2b_2\end{bmatrix}$$

The [[Trace]] of a Kronecker product of matrices is $$tr(A\bigotimes B) = tr(A)\bigotimes tr(B)$$while the [[Determinant]] is $$det(A\bigotimes B) =  (det\ A)^m (det\ B)^n$$where $n$ is the dimension of $A$ and $m$ of $B$. 

**Reminder:**
The Kronecker product is a binary operation on two matrices of arbitrary size, resulting in a block matrix of larger size that contains all the possible products of the entries of the two matrices.
The [[Matrix Product]] is a binary operation on two matrices of compatible sizes, resulting in a new matrix whose entries are computed as the dot product of the corresponding row and column vectors.