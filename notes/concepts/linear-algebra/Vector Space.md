A **Vector Space** is a set of elements (vectors) that may be added together and multiplied ("scaled") by numbers called **scalars**.
Vector spaces generalize **Euclidean vectors**, geometric objects with a given **magnitude** (or length) and a **direction**. 

**A vector space over a field $F$ is a non-empty set $V$ together with two binary operations that satisfy the eight axioms listed below.** 
In this context the elements in $V$ are called **vectors** and the elements in $F$ are called **scalars**. 

The two binary operations are:
- **vector addition:** Assigns to any two vectors $\mathbf{v}$ and $\mathbf{w}$ in $V$ a third vector in $V$ which is commonly written as $\mathbf{v} + \mathbf{w}$, and called the sum of these two vectors. 
- **scalar multiplication:** Assigns to any scalar $a$ in $F$ and any vector $\mathbf{v}$ in $V$ another vector in $V$, which is denoted as $a\mathbf{v}$ 

We work with **column vectors**, such as $$\mathbf{v} =\begin{bmatrix}\alpha_1 \\ . \\ . \\ . \\ . \\ \alpha_n\end{bmatrix}$$ and with $\mathbf{v}^\top$ we indicate the transposed vector, the "associated" row vector $$\mathbf{v}^\top = \begin{bmatrix}\alpha_1 & . &. &. & \alpha_n\end{bmatrix}$$
To have a vector space the following eight axioms must be satisfied for every $\mathbf{u}, \mathbf{v} \in V$ and $a$, $b \in F$
- **associativity of vector addition:** $\mathbf{u} + (\mathbf{v} + \mathbf{w}) = (\mathbf{u} + \mathbf{v}) + \mathbf{w}$ 
- **commutativity of vector addition:** $\mathbf{u} + \mathbf{v} = \mathbf{v} + \mathbf{u}$
- **identity element of vector addition:** There exists an element $\mathbf{0} \in V$, called the **zero vector**, such that $\mathbf{v} + \mathbf{0} = \mathbf{v}$ for every $\mathbf{v} \in V$ 
- **inverse element of vector addition:** For every $\mathbf{v} \in V$ there exists an element $-\mathbf{v} \in V$, called the **additive inverse** of $\mathbf{v}$, such that $\mathbf{v} + (-\mathbf{v}) = 0$ 
- **compatibility of scalar multiplication with field multiplication:** $a(b\mathbf{v}) = (ab)\mathbf{v}$ 
- **identity element of scalar multiplication:** $1\mathbf{v} = \mathbf{v}$, where $1$ denotes the **multiplicative identity** in $F$
- **distributivity of scalar multiplication wrt vector addition:** $a(\mathbf{u}+\mathbf{v}) = a\mathbf{u} + a\mathbf{v}$ 
- **distributivity of scalar multiplication wrt field addition:** $(a+b)\mathbf{v} = a\mathbf{v} + b\mathbf{v}$ 

For every $\mathbf{v} \in V$ and for every $s \in F$ we have, thanks to the axioms, the following properties: 
- $0\mathbf{v} = \mathbf{0}$
- $s\mathbf{0} = \mathbf{0}$
- $(-1)\mathbf{v} = -\mathbf{v}$
- $s\mathbf{v} = 0 \implies s = 0 \lor \mathbf{v} = \mathbf{0}$ 

The **subtraction of two vectors** can be defined as $\mathbf{v} - \mathbf{w} = \mathbf{v} + (-\mathbf{w})$.

We will use the **complex vector space**, which is a vector space where $F = \mathbb{C}$, the set of [[Complex Numbers]]
A vector space can be infinite, but in most application in quantum computation, **finite vector spaces** are used and denoted by $\mathbb{C}^n$. 
In this case the vectors have $n$ complex entries. 
