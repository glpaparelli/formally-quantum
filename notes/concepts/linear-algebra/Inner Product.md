The **inner product** is a binary operation $(.,.): V \times V \rightarrow \mathbb{C}$ which obeys the following properties: 
- the inner product is **linear in the second argument**: $$ (\mathbf{v}, \Sigma_{i=1}^n \ a_i\mathbf{v}_i) = \Sigma_{i=1}^n \ a_i(\mathbf{v}, \mathbf{v}_i)$$
- $(\mathbf{v_1}, \mathbf{v_2}) = (\mathbf{v_2},\mathbf{v_1})^*$, where $(\mathbf{v_2}, \mathbf{v_1})^* \in \mathbb{C}$ is the **conjugate** of $(\mathbf{v_1}, \mathbf{v_2}) \in \mathbb{C}$  
- $(\mathbf{v}, \mathbf{v}) >= 0$ where the equality holds if and only if $\mathbf{v} = 0$ 

There is more than one way to define an inner product on a [[Vector Space]]. 
In the [[Complex Numbers]] vector space $\mathbb{C}^n$ the most used inner product is defined as follows: 
Given two vectors $\mathbf{v}, \mathbf{w}$ 
$$ \mathbf{v} = \begin{bmatrix} a_1 \\ . \\ . \\ . \\ a_n \end{bmatrix} , \ \ \mathbf{w} = \begin{bmatrix} b_1 \\ . \\ . \\ . \\ b_n \end{bmatrix}$$We define their inner product as:
$$(\mathbf{v}, \mathbf{w}) = \Sigma_{i=1}^n \ a^*_ib_i$$
This expression is equivalent to the matrix product of the transpose-conjugate vector, which is usually denoted by $\mathbf{v}^\dagger$, by $\mathbf{w}$. 

Note that: $$(\mathbf{u}, \mathbf{u}) = \Sigma_i|u_i|^2\geq0$$