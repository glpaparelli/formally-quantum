The binary gate $N_c$, is called **controlled not gate** or **CNOT gate**. 
It corresponds to a permutation of [[Basis]] vectors $|00\rangle \rightarrow |00\rangle,\ |01\rangle\rightarrow|01\rangle,\ |10\rangle\rightarrow|11\rangle,\ |11\rangle\rightarrow|10\rangle$. 

Its action can be described as follows: if the first bit is $0$ do nothing, else apply the [[Pauli Gates - X, Y, Z#X Gate|NOT Gate]] to the second bit. 
In this sense, the first bit controls the action of the second one. 
$$N_c = \begin{bmatrix}I & 0 \\ 0 & N\end{bmatrix}$$where $I$ is the identity matrix and $N$ is the NOT gate. 

More generally, for each unary gate S, there is a corresponding binary controlled gate $S_c$, hence we have [[CHadamard Gate]], [[CV Gate]] and [[CW Gate]]