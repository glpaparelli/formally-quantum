We use the [[Dirac Notation]] to represent vectors.

**The state space of a composite quantum system is the tensor product of the state spaces of its components** ([[4th Postulate - Composition of Systems]]).

Let $V$ and $W$ be two [[Hilbert Space]]s with [[Basis]] $\{|v_1\rangle,\dots, |v_m\rangle\}$ and $\{|w_1\rangle, \dots, |w_n\rangle\}$, respectively.
The **tensor product** of $V$ by $W$, denoted by $V\bigotimes W$, is an $m\times n$ Hilbert space, for which the set $\{|v_1\rangle\bigotimes|w_1\rangle,\dots, |v_m\rangle\bigotimes|w_n\rangle\}$ is a basis. 

The tensor product of a vector $|v\rangle \in V$ and a vector $|w\rangle \in W$ such as $|v\rangle \bigotimes |w\rangle$, also denoted with $|v\rangle|w\rangle$ or $|v,w\rangle$ or $|vw\rangle$, can be calculated explicitly via the [[Kronecker Product]]. 

A generic vector in $V \bigotimes W$ is a linear combination of vectors $|v_i\rangle \bigotimes |w_j\rangle$, that is, if $|\psi\rangle \in V \bigotimes W$ then $$|\psi\rangle = \Sigma_{i=1}^m \Sigma_{j=1}^n\ a_{ij}|v_i\rangle\bigotimes|w_j\rangle$$The coefficients $a_{ij}$ are the scalars that multiply each basis vector $|v_i\rangle\bigotimes|w_j\rangle$ in the linear combination that represents the generic vector $|\psi\rangle$ in the tensor product space $V\bigotimes W$. 
In other words, $a_{ij}$ are the coefficients of the expansion of $|\psi\rangle$ in the basis formed by the tensor product of the basis vectors of $V$ and $W$.

The tensor product is **bilinear:** linear in each argument: 
- $|v\rangle \bigotimes \ (a|w_1\rangle+b|w_2\rangle) = a|v\rangle \bigotimes |w_1\rangle + b|v\rangle \bigotimes|w_2\rangle$ 
- $(a|v_1\rangle + b|v_2\rangle)\bigotimes |w\rangle = a|v_1\rangle\bigotimes |w\rangle + b|v_2\rangle\bigotimes |w\rangle$ 

A scalar can always be factored out to the beginning of the expression: $$a(|v\rangle \bigotimes |w\rangle)=(a|v\rangle)\bigotimes|w\rangle=|v\rangle\bigotimes \ (a|w\rangle)$$
The tensor product of a [[Linear Transformation]] $\mathcal{A}$ in $V$ by a linear operator $\mathcal{B}$ in $W$, denoted by $\mathcal{A}\bigotimes\mathcal{B}$, is a linear operator in $V\bigotimes W$ defined by $$(\mathcal{A}\bigotimes \mathcal{B})(|v\rangle \bigotimes |w\rangle)=(\mathcal{A}|v\rangle)\ \bigotimes\ (\mathcal{B}|w\rangle)$$**Said easy**: the vector produced by the linear operator obtained by the tensor product on two linear operators $\mathcal{A}, \mathcal{B}$ on a vector $|v\rangle \bigotimes |w\rangle \in V \bigotimes W$ is equal to the tensor product of $\mathcal{A}$ on $|v\rangle$ and $\mathcal{B}$ on $|w\rangle$.

A generic linear operator in $V\bigotimes W$ can be written as a linear combination of operators of the form $\mathcal{A}\bigotimes \mathcal{B}$, but an operator in $V\bigotimes W$ cannot be factored out in general.
This means that a generic linear operator in $V \bigotimes W$ can indeed be written as a linear combination of tensor products of operators on $V$ and $W$, but not necessarily as a simple linear combination of individual operators acting solely on $V$ or $W$.

This definition can be extended to operators $\mathcal{A}:V\rightarrow V'$ and $\mathcal{B}:W\rightarrow W'$. 
In this case the tensor product of these operators is of type $(\mathcal{A}\bigotimes\mathcal{B}):(V\bigotimes W)\rightarrow(V'\bigotimes W')$. 

In quantum mechanics it is very common to use operators in the form of **external product** (aka [[Outer Product]]), for example, using the [[Matrix Representation]], $A = |v\rangle\langle v|$ and $B=|w\rangle\langle w|$. 
The tensor product of $A$ by $B$ can be represented by the following equivalent ways: 
$$
\begin{align}
A \bigotimes B = \\(|v\rangle\langle v|)\bigotimes (|w\rangle \langle w|) = \\ |v\rangle\langle v|\bigotimes|w\rangle\langle w| =\\ |v, w\rangle\langle v,w| \ \ \  \
\end{align}
$$(remember the notation: $|v,w\rangle$ is the tensor product between $|v\rangle,  |w\rangle$)

If $A_1$ and $A_2$ are operators in $V$ and $B_1, B_2$ are operators in $W$, then the composition or the matrix product of the matrix representations obey the property $$(A_1\bigotimes B_2)(A_2 \bigotimes B_2)= (A_1A_2)\bigotimes (B_1B_2)$$
The [[Inner Product]] of $|v_1\rangle \bigotimes |w_1\rangle$ by $|v_2\rangle \bigotimes |w_2$ is defined as $$(|v_1\rangle \bigotimes |w_2), |v_2\rangle \bigotimes |w_2\rangle)= \langle v_1|v_2\rangle\langle w_1|w_2\rangle$$
The inner product of vectors written as a linear combination of [[Basis]] vectors are calculated by applying the linear property in the second argument and the conjugate-linear property in the first argument of the inner product, for example: $$((\Sigma_{i=1}^n \ a_i|v_i\rangle)\bigotimes |w_1\rangle, |v\rangle \bigotimes |w_2\rangle) = (\Sigma_{i=1}^n\ a_i^*\langle v_i|v\rangle)\langle w_1|w_2\rangle$$
The inner product definition implies that $$|| |v\rangle || \bigotimes |||w\rangle|| = || |v\rangle|| \ \cdot\ |||w\rangle||$$ In particular, the [[Norm]] of the tensor product of unit-norm vectors is a unit-norm vector. 

The tensor product is an **associative** and **distributive** operation, but noncommutative, that is $|v\rangle \bigotimes |w\rangle \neq |w\rangle \bigotimes |v\rangle$ if $|v\rangle \neq |w\rangle$. 

Most operations on a tensor product are performed term by term, such as $$(A\bigotimes B)^\dagger= A^\dagger \bigotimes B^\dagger$$
If both $A$ and $B$ are special operators of the same type, then the tensor product $A\bigotimes B$ is also a special operator of the same type. 
For example, the tensor product of [[Hermitian Operator]]s is an Hermitian operator.

### Special Cases
This part is from [[Towards a Quantum Programming Language]]

1. The tensor product $\mathbf{w} = \mathbf{u}\bigotimes\mathbf{v} \in \mathbb{C}^{nm}$ of two vectors $\mathbf{u} \in \mathbb{C}^n, \mathbf{v}\in \mathbb{C}^m$ is defined by $$\mathbf{w}_{(i,j)}=\mathbf{u}_i \mathbf{v}_j$$
2. The tensor product $C = A \bigotimes B\in \mathbb{C}^{nm \times nm}$ of two matrices is defined by $$c_{(i,j),(i',j')}=a_{ii'}b_{jj'}$$Here we order the pairs $(i,j)$ lexicographically; thus, for instance ![[tensor-product-matrices.png | center | 300]]
