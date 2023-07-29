The [[Quantum Gate]]s known as **the Pauli Gates** $(X, Y, Z)$ are the three **Pauli matrices** $(\sigma_x, \sigma_y, \sigma_z)$ and act on a single [[Qubit]]. 
The Pauli $X, Y, Z$ equate, respectively, to a rotation around the axes $x, y$ and $z$ of the [[Bloch Sphere]] by $\pi$ radians.

##### X Gate
The **X Gate** switches between the two basis states and it is represented with an $X$ $$X|0\rangle = |1\rangle, \ \ \ X|1\rangle = |0\rangle$$The X Gate is also called the **NOT Gate**.
In the matrix representation we have:$$X = \begin{bmatrix}0 & 1 \\1 & 0\end{bmatrix}$$And we can check its operation on the two basis states: 
- $\begin{bmatrix}0 & 1 \\1 & 0\end{bmatrix}\begin{bmatrix} 1 \\ 0\end{bmatrix} = \begin{bmatrix} 0 \\ 1\end{bmatrix}$ 
- $\begin{bmatrix}0 & 1 \\1 & 0\end{bmatrix}\begin{bmatrix} 0 \\ 1\end{bmatrix} = \begin{bmatrix} 1 \\ 0\end{bmatrix}$

**On an arbitrary state** we get $$\begin{bmatrix}0 & 1 \\1 & 0\end{bmatrix}\begin{bmatrix} \alpha \\ \beta\end{bmatrix} = \begin{bmatrix} \beta \\ \alpha\end{bmatrix}$$
**Geometrically** the NOT gate corresponds to the symmetry of axis $\pi/4$. 

##### Y Gate
$$Y = \sigma_y = \begin{bmatrix}0 & -i \\i & 0\end{bmatrix}$$
The **Y Gate** maps $|0\rangle$ to $i|1\rangle$ and $|1\rangle$ to $-1|0\rangle$

##### Z Gate
$$Z = \sigma_z = \begin{bmatrix}1 & 0 \\0 & -1\end{bmatrix}$$
The Z leaves the basis state $|0\rangle$ unchanged and maps $|1\rangle$ to $|-1\rangle$.
Due to this nature, the Z Gate is sometimes called **phase-flip.**