This part is from [[Towards a Quantum Programming Language]]

Recall that $D_n$ is the set of [[Density Operator#Density Matrix|Density Matrices]] of dimension $n$ $$D_n=\{A\in\mathbb{C}^{n\times n}\}$$with $A$ [[Positive Operator#Positive Matrix|Positive]] [[Hermitian Operator#Hermitian Matrix|Hermitian matrix]] and [[Trace]]$(A)=\leq 1$ 

#### Löwner Partial Order
For matrices $A, B \in \mathbb{C}^{n\times n}$, we define $A\sqsubseteq B$ if the matrix $B-A$ is a positive matrix. 

It is immediately obvious that $\sqsubseteq$ defines a [[Partial Order]] on the set $\mathbb{C}^{n\times n}$. This partial order is known in literature as the **Löwner Partial Order** and it is commonly used in an area of linear programming known as semidefinite programming. 
When restricted to the set $D_n$ of density matrices, this partial order has the zero matrix $0$ as its least element. We also denote the zero matrix by $\bot$. 

##### Proposition 3.6
The [[Poset]] $(D_n, \sqsubseteq)$ is a [[Complete Partial Order]], i.e., it has [[Least Upper Bound]]s of increasing sequences. 
**proof to do.**

##### Remark 3.7
The poset $(D_n, \sqsubseteq)$ is not a [[Lattice]] for $n\geq 2$; in fact, it does not even have least upper bounds of bounded sets 

##### Remark 3.8
For any increasing sequence in $D_n$, $A$ is the least upper bound if and only if $A$ is the [[Topological Limit]] of the sequence, with respect to the [[Standard Topology]] on $\mathbb{C}^{n\times n}$.
It follows, among other things, that a monotone function $f:D_n\rightarrow D_n$ is [[Scott Continuous]] (i.e., it preserves least upper bounds of increasing sequences) if it is topologically continuous. 
The converse is not in general true. 

##### Remark 3.9
For a [[Density Operator#Density Matrix|Density Matrix]] such as![[density-matrix-cpo-1.png | center | 150]]with $B, C \neq 0$ we have: ![[density-matrix-cpo-2.png | center | 550]]but: ![[density-matrix-cpo-3.png | center]]
The latter inequalities fails because the difference of the two matrices has null entries on the diagonal, and thus can be [[Positive Operator#Positive Matrix|positive]] only if the corresponding non-diagonal entries also vanish. 