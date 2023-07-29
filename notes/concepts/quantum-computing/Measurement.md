[[3rd Postulate - Quantum Measurement]]
This part is from [[Towards a Quantum Programming Language]]. 

The second fundamental operation on the state of a quantum system is known as **measurement**.
This occurs when we try to observe the value of a [[Qubit]] and convert it into a classical bit. 


### 1-Qubit Measurement
Consider for instance the state of a single qubit $q = \alpha|0\rangle + \beta|1\rangle$. 
Let's assume that the amplitudes have been normalized such that $|\alpha|^2+|\beta|^2 = 1$. 
The act of measuring this quantum bit will yield an answer which is either $0$ or $1$ with probability $|\alpha|^2$ and $|\beta|^2$ respectively. 
Moreover the measurement causes the quantum state to **collapse**: after the measurement the quantum state will have changed to either $|0\rangle$ or $|1\rangle$, depending on the result of measurement. 
If we measure again we will have always the same answer. 

### 2-Qubit Measurement
The situation is more complex if more than one qubit is involved. Consider a two-qubit system in the state $\alpha|00\rangle + \beta|01\rangle + \gamma|10\rangle + \delta|11\rangle$. 
We again assume that the amplitudes have been normalized. 
If we measure the value of the first bit, one of the following things will happen: 
- with probability $|\alpha|^2 + |\beta|^2$ the result of the measurement will be $0$ and the quantum state will collapse to $\alpha|00\rangle + \beta|01\rangle$
- with probability $|\gamma|^2+ |\delta|^2$ the result of the measurement will be 1 and the quantum state will collapse to $\gamma|10\rangle + \delta|11\rangle$ 

Note that only the portion of the quantum state pertaining to the bit that we are observing collapses. 

If we were observing the second bit instead the observed answer would be $0$ with probability $|\alpha|^2 + |\gamma|^2$ and $1$ with probability $|\beta|^2+|\gamma|^2$, and the quantum state would collapse to $\alpha|00\rangle + \gamma|10\rangle$ or $\beta|01\rangle + \delta|11\rangle$ respectively. 

Now, let's see what happens if we measure the second qubit after the second one. 
The situation can be summarized in the following diagram: 
![[2-qb-measurement.png | center | 700]]

In this tree, the nodes are labelled with states and the transitions are labelled with probabilities. 
Note that the overall probability of observing $00$ as the result of the two measurements is $p_0p_{00} = |\alpha|^2$, and the probability of observing $01$ is $p_0p_{01} = |\beta|^2$, and so forth. 
In particular these probabilities are independent of the order of measurement; thus the result does not depend on which qubit we measure first (or if we measure them at the same time). 
This name of this phenomenon is that the two measurement **commute**. 
In quantum computation this phenomenon always happens. 

We mentioned that it is customary to normalize quantum states so that the sum of the squares of the amplitudes is $1$.
However, in light of the above diagram, we find that it is often more convenient to normalize states differently: 

#### Convention 3.3 (Normalization Convention)
> We normalize each state in such a way that the sum of the squares of the amplitudes is equal to the total probability that this state is reached.

With this convention it becomes unnecessary to renormalize the state after a measurement has been performed. 
We will see how this simplifies our computations. 
