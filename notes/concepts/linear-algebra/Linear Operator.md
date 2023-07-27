We use the [[Dirac Notation]] to represent vectors.

Let $V$ and $W$ be vector spaces, $\{|v_1\rangle,\ \dots,\ |v_n\rangle\}$ a basis for $V$, and $\mathcal{A}$ a function $\mathcal{A}:V\rightarrow W$ that satisfies $$\mathcal{A}(\Sigma_ia_i|v_i\rangle)= \Sigma_i\ a_i\mathcal{A}(|v_i\rangle)$$for any complex number $a\in\mathbb{C}$.

$\mathcal{A}$ is called **linear operator** from $V$ to $W$. 
The term **linear operator in** $\mathbf{V}$ means that both the domain and codomain of $\mathcal{A}$ is $V$. 

The **composition of linear operators** $\mathcal{A}: V_1 \rightarrow V_2$ and $\mathcal{B}: V_2 \rightarrow V_3$ is also a liner operator $\mathcal{C}:V_1\rightarrow V_3$ obtained by the composition of their functions: $\mathcal{C}(|v\rangle)=\mathcal{B}(\mathcal{A}(|v\rangle))$.
The **sum of two linear operators**, both from $V$ to $W$ is naturally defined by the formula $(\mathcal{A}+\mathcal{B})(|v\rangle)=\mathcal{A}(|v\rangle)+\mathcal{B}(|v\rangle)$ . 
The **identity operator** $\mathcal{I}$ in $V$ is a linear operator such that $\mathcal{I}(|v\rangle)=|v\rangle$ for all $|v\rangle \in V$. 
The **null operator** $\mathcal{O}$ in $V$ is a linear operator such that $\mathcal{O}(|v\rangle)=\mathbf{0}$ for all $|v\rangle \in V$. 
The **rank** or of a linear operator $\mathcal{A}$ in $V$ is the dimension of the image of $\mathcal{A}$. 
The **kernel** of a linear operator $\mathcal{A}$ in $V$ is the set of all vectors $|v\rangle$ for which $\mathcal{A}|v\rangle = \mathbf{0}$ . 

A linear operator can be seen as a **matrix** thanks to its [[Matrix Representation]]

Any "kind" of linear operator (such as [[Unitary Operator]], [[Positive Operator]], ...) can also be defined as [[Linear Transformation]], since a linear operator is a special kind of linear transformation.