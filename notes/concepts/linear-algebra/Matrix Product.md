Matrix multiplication is a binary operation that produces a matrix from two matrices.
The resulting matrix, known as the matrix product, has the number of rows of the first and the number of columns of the second matrix. 
For matrix multiplication, the number of columns in the first matrix must be equal to the number of rows in the second matrix.

The product of matrices $A$ and $B$ is denoted as $AB$. If $A$ is an $m \times n$ matrix and $B$ is an $n \times p$ matrix, the matrix product $C = AB$ is defined to be the $m \times p$ matrix such that for $i \in [1,m]$ and $j = \in [1,p]$ the entry in the $i$-th row and $j$-th column of $C$ is obtained by multiplying term-by-term the entries of the $i$-th row of $A$ and the $j$-th column of $B$, and summing these $n$ products.

Matrix multiplication is not commutative, meaning that $AB$ is not necessarily equal to $BA$. 
However, it is associative, meaning that $(AB)C = A(BC)$ for any matrices $A$, $B$, and $C$ of appropriate sizes. 

**More formally:**
Given the $m\times n$ matrix $A$ and the $n\times p$ matrix $B$ ![[matrix-product-1.png | center | 550]]The matrix product $C = AB$ is defined to be the $m\times p$ matrix ![[matrix-product-2.png | center | 300]]such that $$c_{ij}=a_{i1}b_{1j}+ a_{i2}b_{2j} + \dots + a_{in}b_{nj}= \Sigma_{k=1}^n\ a_{ik}b_{kj}$$for $i = 1,\ \dots,\ m$ and $j = 1,\ \dots,\ p$. 

