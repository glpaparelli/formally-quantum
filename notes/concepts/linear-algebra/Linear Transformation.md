A **Linear Transformation** is a function that maps vectors from one [[Vector Space]] to another while preserving the linear structure of the vector spaces. 
A **Linear Operator** (technically) is a specific type of linear transformation where the domain and codomain spaces are the same. 

In other words, **a linear operator is a linear transformation that maps vectors from a vector space back to the same vector space**. 

> The terms "linear transformation" and "linear operator" are used interchangeably, in this notes, unless stated otherwise. 

---

**A linear operator is a function that maps one [[Vector Space]] to another while preserving the linear structure of the vector space.**
In other words, it is a function that satisfies two key properties: **additivity** and **homogeneity**.

The **additivity property** states that for any vectors $\mathbf{x}$ and $\mathbf y$ in the domain of the linear operator, the function applied to the sum of $\mathbf x$ and $\mathbf y$ is equal to the sum of the function applied to $\mathbf x$ and the function applied to $\mathbf y$. 
Mathematically, it can be expressed as: $f(\mathbf x + \mathbf y) = f(\mathbf x) + f(\mathbf y)$.

The **homogeneity property** states that for any vector $\mathbf x$ in the domain of the linear operator and any scalar $c$, the function applied to the scalar multiple of $\mathbf x$ is equal to the scalar multiple of the function applied to $\mathbf x$. 
Mathematically, it can be expressed as: $f(c\mathbf x) = cf(\mathbf x)$.

**These two properties ensure that the linear operator preserves vector addition and scalar multiplication, which are fundamental operations in vector spaces.** 

A linear operator can be seen as a **matrix** thanks to its [[Matrix Representation]]

**More formally:**
We use the [[Dirac Notation]] to represent vectors.
Let $V$ and $W$ be [[Vector Space]]s, $\{|v_1\rangle,\ \dots,\ |v_n\rangle\}$ a [[Basis]] for $V$, and $\mathcal{A}$ a function $\mathcal{A}:V\rightarrow W$ that satisfies $$\mathcal{A}(\Sigma_ia_i|v_i\rangle)= \Sigma_i\ a_i\mathcal{A}(|v_i\rangle)$$for any complex number $a_i\in\mathbb{C}$. $\mathcal{A}$ is called **linear operator** from $V$ to $W$. 
Mind that $\Sigma_i\ a_i|v_i\rangle$ is the representation of any vector $|w\rangle \in V$ as linear combination of the basis.

The **composition of linear operators** $\mathcal{A}: V_1 \rightarrow V_2$ and $\mathcal{B}: V_2 \rightarrow V_3$ is also a liner operator $\mathcal{C}:V_1\rightarrow V_3$ obtained by the composition of their functions: $\mathcal{C}(|v\rangle)=\mathcal{B}(\mathcal{A}(|v\rangle))$.
The **sum of two linear operators**, both from $V$ to $W$ is naturally defined by the formula $(\mathcal{A}+\mathcal{B})(|v\rangle)=\mathcal{A}(|v\rangle)+\mathcal{B}(|v\rangle)$ . 
The **identity operator** $\mathcal{I}$ in $V$ is a linear operator such that $\mathcal{I}(|v\rangle)=|v\rangle$ for all $|v\rangle \in V$. 
The **null operator** $\mathcal{O}$ in $V$ is a linear operator such that $\mathcal{O}(|v\rangle)=\mathbf{0}$ for all $|v\rangle \in V$. 
The **rank**  of a linear operator $\mathcal{A}$ in $V$ is the dimension of the image of $\mathcal{A}$. 
The **kernel** of a linear operator $\mathcal{A}$ in $V$ is the set of all vectors $|v\rangle$ for which $\mathcal{A}|v\rangle = \mathbf{0}$ . 

**A linear operator is a function that maps one [[Vector Space]] to another while preserving the linear structure of the vector space.**
In other words, it is a function that satisfies two key properties: **additivity** and **homogeneity**.

The **additivity property** states that for any vectors $\mathbf{x}$ and $\mathbf y$ in the domain of the linear operator, the function applied to the sum of $\mathbf x$ and $\mathbf y$ is equal to the sum of the function applied to $\mathbf x$ and the function applied to $\mathbf y$. 
Mathematically, it can be expressed as: $f(\mathbf x + \mathbf y) = f(\mathbf x) + f(\mathbf y)$.

The **homogeneity property** states that for any vector $\mathbf x$ in the domain of the linear operator and any scalar $c$, the function applied to the scalar multiple of $\mathbf x$ is equal to the scalar multiple of the function applied to $\mathbf x$. 
Mathematically, it can be expressed as: $f(c\mathbf x) = cf(\mathbf x)$.

**These two properties ensure that the linear operator preserves vector addition and scalar multiplication, which are fundamental operations in vector spaces.** 

A linear operator can be seen as a **matrix** thanks to its [[Matrix Representation]]

**More formally:**
We use the [[Dirac Notation]] to represent vectors.
Let $V$ and $W$ be [[Vector Space]]s, $\{|v_1\rangle,\ \dots,\ |v_n\rangle\}$ a [[Basis]] for $V$, and $\mathcal{A}$ a function $\mathcal{A}:V\rightarrow W$ that satisfies $$\mathcal{A}(\Sigma_ia_i|v_i\rangle)= \Sigma_i\ a_i\mathcal{A}(|v_i\rangle)$$for any complex number $a_i\in\mathbb{C}$. $\mathcal{A}$ is called **linear operator** from $V$ to $W$. 
Mind that $\Sigma_i\ a_i|v_i\rangle$ is the representation of any vector $|w\rangle \in V$ as linear combination of the basis.

The **composition of linear operators** $\mathcal{A}: V_1 \rightarrow V_2$ and $\mathcal{B}: V_2 \rightarrow V_3$ is also a liner operator $\mathcal{C}:V_1\rightarrow V_3$ obtained by the composition of their functions: $\mathcal{C}(|v\rangle)=\mathcal{B}(\mathcal{A}(|v\rangle))$.
The **sum of two linear operators**, both from $V$ to $W$ is naturally defined by the formula $(\mathcal{A}+\mathcal{B})(|v\rangle)=\mathcal{A}(|v\rangle)+\mathcal{B}(|v\rangle)$ . 
The **identity operator** $\mathcal{I}$ in $V$ is a linear operator such that $\mathcal{I}(|v\rangle)=|v\rangle$ for all $|v\rangle \in V$. 
The **null operator** $\mathcal{O}$ in $V$ is a linear operator such that $\mathcal{O}(|v\rangle)=\mathbf{0}$ for all $|v\rangle \in V$. 
The **rank**  of a linear operator $\mathcal{A}$ in $V$ is the dimension of the image of $\mathcal{A}$. 
The **kernel** of a linear operator $\mathcal{A}$ in $V$ is the set of all vectors $|v\rangle$ for which $\mathcal{A}|v\rangle = \mathbf{0}$ . 






