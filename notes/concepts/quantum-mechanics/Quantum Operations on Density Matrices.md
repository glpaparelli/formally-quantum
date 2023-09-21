This part is from [[Towards a Quantum Programming Language]]

The two kinds of quantum operations ([[Unitary Transformation on QC]]s and [[Measurement]]) can both be expressed with respect to [[Density Matrix#Density Matrix|Density Matrices]].

A unitary transformation $S$ maps a [[Quantum States|pure quantum state]] $\mathbf{u}$ to $S\mathbf{u}$. 
Thus, it maps a pure density matrix $\mathbf{u}\mathbf{u}^\top$ to $S\mathbf{u}\mathbf{u}^\top S^\dagger$. 

---

**Why a Unitary Transformation $S$ maps a pure density matrix $\mathbf{u}\mathbf{u}^\top$ to $S\mathbf{u}\mathbf{u}^\top S^\dagger$**
To see why $\mathbf{uu}^\top$ is mapped to $S \mathbf{uu}^\top S^\dagger$, we can use the definition of a unitary transformation.
A unitary transformation is a linear transformation that preserves the inner product of vectors.
Therefore, for any vectors $\mathbf{u}$ and $\mathbf{v}$, we have $\langle S\mathbf{u},S\mathbf{v}\rangle = \langle \mathbf{u},\mathbf{v}\rangle$.

Now, let's consider the pure density matrix $\mathbf{u}\mathbf{u}^\top$. 

We can write this as $\mathbf{u}\mathbf{u}^\top = \langle \mathbf{u},\cdot\rangle \mathbf{u}$. 
The notation $\langle \mathbf{u},\cdot\rangle$ denotes the inner product of a vector $\mathbf{u}$ with another vector. 
Specifically, if $\mathbf{v}$ is another vector, then $\langle \mathbf{u},\mathbf{v}\rangle$ is the complex scalar obtained by taking the conjugate transpose of $\mathbf{u}$ and multiplying it with $\mathbf{v}$ (which is the definition of the [[Inner Product]] in the [[Vector Space]] $\mathbb{C}^n$).

We can write $\mathbf{u}\mathbf{u}^\top = \langle \mathbf{u},\cdot\rangle \mathbf{u}$ because $\mathbf{u}\mathbf{u}^\top$ is a **rank-$1$ projection operator** that projects onto the one-dimensional subspace spanned by the vector $\mathbf{u}$.
**Reminder:** *kets* $|.\rangle$ are column matrices, *bras* $\langle .|$ are row matrices.
**A rank-$1$ projector can be seen as a matrix that takes a vector and return a vector multiplied by a scalar.**
This matrix can be seen as a *ket-bra* vector product  $|u\rangle\langle u|$, where the bra vector $\langle u|$ has the function of going in the inner product with the vector that you pass to the matrix, giving a complex scalar. 
Thus you remain with a scalar that multiplies the *ket* vector $|u\rangle$. 
Therefore, when we take the inner product of $\mathbf{u}$ with another vector $\mathbf{v}$ we get $\langle \mathbf{u},\mathbf{v}\rangle = \mathbf{u}^\dagger \mathbf{v}$, which is a complex scalar. 
Multiplying this scalar with the vector $\mathbf{u}$ gives us $\langle \mathbf{u},\cdot\rangle \mathbf{u}$
**Said easy:** $\langle \mathbf{u},\cdot\rangle \mathbf{u}$ is a shorthand notation for the rank-$1$ projection operator $\mathbf{u}\mathbf{u}^\top$, which projects onto the one-dimensional subspace spanned by the vector $\mathbf{u}$.

Applying the unitary transformation $S$ to this density matrix, we get $S\mathbf{u}\mathbf{u}^\top S^\dagger = S(\langle \mathbf{u},\cdot\rangle \mathbf{u})S^\dagger = \langle S\mathbf{u},\cdot\rangle S\mathbf{u}S^\dagger = (S\mathbf{u})(S\mathbf{u})^\dagger$
Therefore, we see that $\mathbf{uu}^\top$ is mapped to $S \mathbf{uu}^\top S^\dagger$ because a unitary transformation preserves inner products and $\mathbf{u}\mathbf{u}^\top$ can be written as a rank-$1$ projection operator.
$\square$

---

Moreover a unitary transformation extends linearly to mixed states, and thus, it takes any mixed density matrix $A$ to $SAS^\dagger$.

Now consider the effect of measurement on a density matrix. 
We begin by considering a pure state $\mathbf{u}\mathbf{u}^\top$, for some unit ([[Norm|norm]] $=1$) vector $\mathbf{u}$. 
Suppose that we use the [[Horizontal-Vertical Concatenation]] 
Suppose that:$$\mathbf{u}= \begin{bmatrix}\mathbf{v}\\\mathbf{w}\end{bmatrix},\ \text{therefore}\ \ \mathbf{u}\mathbf{u}^\top =  \begin{bmatrix}\mathbf{v}\mathbf{v}^\top & \mathbf{v}\mathbf{w}^\top\\\mathbf{w}\mathbf{v}^\top & \mathbf{w}\mathbf{w}^\top\end{bmatrix}$$Assuming that the rows of $\mathbf{u}$ are ordered to the [[Qubit#Convention 3.1|lexicographic convention]], then we perform a measurement on the first bit, the outcome will be $\begin{bmatrix} \mathbf{v}\\ \mathbf{0}\end{bmatrix}$ with probability $||\mathbf{v}||^2$ and $\begin{bmatrix} \mathbf{0}\\ \mathbf{w}\end{bmatrix}$ with probability $||\mathbf{w}||^2$. 
In density matrix notation the outcome will be ![[density-matrix-ops-1.png| center | 350]]where the first matrix occurs with probability $||\mathbf{v}^2||$ and the second with probability $||\mathbf{w}||^2$. 
Notice that the probability that each matrix occurs is equal to its [[Trace]]: $||\mathbf{v}||^2 = tr(\mathbf{v}\mathbf{v}^\top)$ (idem for $\mathbf{w}$).
Thus, the [[Measurement#Convention 3.3 (Normalization Convention)|normalization convention]] extends naturally to density matrices: the density matrix of a state shall be normalized in such a way that its trace corresponds to the overall probability that this state is reached. 
With this convention each of the two possible outcomes of a measurement is a linear function of the incoming state. 

The [[Measurement]] operation extends linearly form pure to mixed states. 
Thus, performing a measurement on a mixed state of the form ![[density-matrix-ops-2.png | center | 150]]results in one of the two states ![[density-matrix-ops-3.png | center | 400]]where each of the two matrices occurs with probability equal to its trace. 

If one ignores the classical bit information that is observed from the measurement, then the resulting state is a mixed state ![[density-matrix-ops-4.png | center | 200]]Thus, collapsing a quantum bit (measuring it while ignoring the result) corresponds to setting a certain region of the density matrix to $0$. 

We have seen that the effect of the two fundamental operations of quantum mechanics, [[Unitary Transformation on QC]]s and [[Measurement]]s. can be described in terms of their action on density matrices. 
Since unitary transformations and measurements are our only means of interacting with a quantum state, it follows that there is no observable difference between mixed states which have the same density matrix representation. 

