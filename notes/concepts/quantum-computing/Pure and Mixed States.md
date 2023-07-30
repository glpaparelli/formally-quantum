This part is from [[Towards a Quantum Programming Language]]. 
[[Pure State]]s, [[Mixed State]]s. 

We know that a quantum system at any given time can be described by its state vector $\mathbf{u}\in \mathbb{C}^{2^n}$, modulo a scalar multiple ([[1st Postulate - State Space]], [[Qubit]]).
However, an outside observer might have incomplete knowledge about the state of the system. 
For instance, suppose that we know that a given system is either in state $\mathbf{u}$ or in state $\mathbf{v}$, with equal probability. 
We use the ad hoc notation $\frac{1}{2}\{\mathbf{u}\} + \frac{1}{2}\{\mathbf{v}\}$ to describe this situation. 

In general we write $\lambda_1\{\mathbf{u}_1\}+ \dots + \lambda_m\{\mathbf{u}_m\}$ for a system which, from the viewpoint of some observer, is known to be in state $\mathbf{u}_i$ with probability $\lambda_i$, with $\Sigma_i \lambda_i = 1$. 
Such a probability distribution on quantum states is called a **mixed state**. 
The underlying quantum states, such as $\mathbf{u}$ are called **pure states** to distinguish them from mixed states. 

It is important to realize that a mixed state is a description of an observers knowledge of the state of a quantum system, rather than a property of the system itself. 
In particular, a given system might be in two different mixed states from the viewpoints of two different observers. Thus, the notion of mixed states does not have an independent physical meaning. 
Physically, any quantum system is in a (possibly unknown) pure state at any given time. 

[[Unitary Transformation]]s operate component-wise on mixed states. Thus, unitary transformation $S$ maps a mixed state $\lambda_1\{\mathbf{u}_1\}+ \dots + \lambda_m\{\mathbf{u}_m\}$ to $\lambda_1\{S\mathbf{u}_1\}+ \dots + \lambda_m\{S\mathbf{u}_m\}$ 

The collapse of a [[Qubit]] takes pure states to mixed states. For instance, if we [[Measurement|measure]] a quantum bit in a state $\alpha|0\rangle + \beta|1\rangle$ but ignore the outcome of the measurement, the system enters (from our point of view) in the mixed state $|\alpha|^2\{|0\rangle\} + |\beta|^2\{|1\rangle\}$

