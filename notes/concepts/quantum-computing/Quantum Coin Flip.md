We use the [[Dirac Notation]] to represent vectors.

Let us consider an experiment that could not be explained in a natural way using classical physics.

The experiment involves **photons:**
- elementary particles (quantum) of light
- massless 
- move at the speed of light in vacuum 
- exhibit wave-particle duality (behave featuring properties of both waves and particles)

Experimental set-up consists of a **photon source**, a **beam splitter** (implemented using half-silvered mirror), and a pair of **photon detectors**

### The First Experiment
![[coin-flip-1.png | center | 400]]

We send a series of individual photons along a path from the photon source towards the beam splitter.
We expect two behaviors: the beam splitter either transmits or reflects the photon. 

Then we can model the beam splitter as **flipping a fair coin**, and choosing whether to transmit or reflect the photon based on the result of the coin-flip, whose outcome determines whether the photon is transmitted or reflected.

A beam splitter behaves similarly to a fair coin
- head (state 0): transmitted, with half probability the photon is transmitted and the state do not change
- tail (state 1): reflected, with half probability the photon is reflected, and the state is flipped

Our **prediction** is so have the following result:
![[coin-flip-2.png | center | 400]]
**The experiments confirms our expectation.**

### The Second Experiment
We extend the previous experiment with two mirrors and another beam splitter 
![[coin-flip-3.png | center | 450]]

In this setup we have three photon detectors. 
Our **prediction** is to have a photon
- in A with a probability of $\frac{1}{2}$ 
- in B1 and B2 with probabilities $\frac{1}{4}$ each

**The experiments confirm our expectations.**

### The Third Experiment 
In the third experiment we remove the photon detector A and obtain the following setup:
![[coin-flip-4.png | center | 400]]

Our **prediction** is to observe the photons in B1 and B2 almost evenly:
![[coin-flip-5.png | center | 400]]

**Let us explain our prediction with mathematical calculation:**
- we consider a photon as a 2-state system:
	- **state 0:** transmitted
	- **state 1:** reflected
- we use a vector representation
	- $|0\rangle = \begin{bmatrix} 1 \\ 0\end{bmatrix}$, photon in state 0
	- $|1\rangle = \begin{bmatrix} 0 \\ 1\end{bmatrix}$, photon in state 1
- **uncertain states** will be represented by a **linear combinations** of $|0\rangle$ and $|1\rangle$
	- $a_0|0\rangle + a_1|1\rangle = a_0\begin{bmatrix} 1 \\ 0\end{bmatrix} + a_1\begin{bmatrix} 0 \\ 1\end{bmatrix} = \begin{bmatrix} a_0 \\ a_1\end{bmatrix}$ 
	- $a_0, a_1$ denote **probabilities** to find the photon in state $|0\rangle$, $|1\rangle$ respectively
- since we should find the photon in exactly one path we must have $a_0 + a_1 = 1$ 
- we model the beam splitter as randomly selecting whether the photon will be transmitted (and continue on the state $|0\rangle$) or will be reflected and continue in the state $|1\rangle$
- at the initial state we are in the state $|0\rangle = \begin{bmatrix} 1 \\ 0\end{bmatrix}$ 
- we flip a fair coin (first beam splitter): the new probabilistic state is expected to be in both states $|0\rangle$ and $|1\rangle$ with probability $1/2$: $$ \frac{1}{2}|0\rangle + \frac{1}{2}|1\rangle = \frac{1}{2}\begin{bmatrix} 1 \\ 0\end{bmatrix} + \frac{1}{2}\begin{bmatrix} 0 \\ 1\end{bmatrix} = \frac{1}{2}\begin{bmatrix} 1 \\ 1\end{bmatrix} = \begin{bmatrix} \frac{1}{2} \\ \frac{1}{2}\end{bmatrix}$$
- the transition of a fair coin can be represented by the matrix TODO $$\begin{bmatrix}\frac{1}{2} & \frac{1}{2} \\\frac{1}{2} & \frac{1}{2}\end{bmatrix}$$
- when the photon passes through the beam splitter we multiply its state vector by this matrix to derive the new state where the photon is expected to be in both states $|0\rangle$ and $|1\rangle$ with half probability $1/2$ $$ \begin{bmatrix}\frac{1}{2} & \frac{1}{2} \\\frac{1}{2} & \frac{1}{2}\end{bmatrix} \begin{bmatrix} 1 \\ 0\end{bmatrix} = \begin{bmatrix} \frac{1}{2} \\ \frac{1}{2}\end{bmatrix} = \frac{1}{2}\begin{bmatrix} 1 \\ 0\end{bmatrix} + \frac{1}{2}\begin{bmatrix} 0 \\ 1\end{bmatrix}  $$
- then we flip the fair coin again, and multiply the new state vector by the same matrix, the new probabilistic state will be the same: $$ \begin{bmatrix}\frac{1}{2} & \frac{1}{2} \\\frac{1}{2} & \frac{1}{2}\end{bmatrix} \begin{bmatrix} \frac{1}{2} \\ \frac{1}{2}\end{bmatrix} = \begin{bmatrix} \frac{1}{2} \\ \frac{1}{2}\end{bmatrix} = \frac{1}{2}\begin{bmatrix} 1 \\ 0\end{bmatrix} + \frac{1}{2}\begin{bmatrix} 0 \\ 1\end{bmatrix}$$
- **Our prediction** to observe the photons in B1 and in B2 almost evenly is explained with mathematical calculation. 

**The experimental results do not agree with our classical intuition:**
![[coin-flip-6.png | center | 450]]

**The "classical" (newtonian) mechanics fails to explain the behaviors of particles.** 

### The Third Experiment, with Quantum Physics
> Quantum Theory is Probability Theory with Negative Numbers
- We can't have negative probabilities. To accommodate this we use a new quantity called **amplitudes**
- To get around the fact that we cannot have negative probabilities and that all our probabilities must add up to $1$ we square our amplitudes to calculate the probabilities. 

Let's see the previous calculations, using quantum mechanics: 
- according to the quantum mechanical description, the beam splitter causes the photon to go into a [[Quantum Mechanics Phenomenas#Superposition]] of both the 0 and 1 states
- mathematically we describe such a superposition by taking a linear combination of the state vectors for the state '0' and '1', where $a_0$ and $a_1$ are now [[Complex Numbers]] (so they can be negative numbers)$$a_0 \begin{bmatrix} 1 \\ 0\end{bmatrix} + a_1 \begin{bmatrix} 0 \\ 1\end{bmatrix} = \begin{bmatrix} a_0 \\ a_1\end{bmatrix}, \ \ \ \ \ a_0, a_1 \in \mathbb{C}$$
- if we were to physically measure the photon to see which state it is in, we will find it in state $|0\rangle$ with probability $|a_0|^2$ and in state $|1\rangle$ with probability $|a_1|^2$ 
- since we should find the photon in exactly one path me must have $|a_0|^2 + |a_1|^2 = 1$

Let's consider again the third experiment: 
- the photon starts in state $|0\rangle = \begin{bmatrix} 1 \\ 0\end{bmatrix}$
- when it passes through the first beam splitter we multiply its state vector by the matrix $$\begin{bmatrix}\frac{1}{\sqrt2} & \frac{1}{\sqrt2} \\\frac{1}{\sqrt2} & -\frac{1}{\sqrt2}\end{bmatrix}$$
- after passing through the first beam splitter it come out in the state $$\begin{bmatrix}\frac{1}{\sqrt2} & \frac{1}{\sqrt2} \\\frac{1}{\sqrt2} & -\frac{1}{\sqrt2}\end{bmatrix} \begin{bmatrix} 1 \\ 0\end{bmatrix} = \begin{bmatrix} \frac{1}{\sqrt2} \\ \frac{1}{\sqrt2}\end{bmatrix} = \frac{1}{\sqrt2}\begin{bmatrix} 1 \\ 0\end{bmatrix} + \frac{1}{\sqrt2}\begin{bmatrix} 0 \\ 1\end{bmatrix} = \frac{1}{\sqrt2}\begin{bmatrix} 1 \\ 1\end{bmatrix}$$
- this result corresponds with the observer behavior that, after going through the first beam splitter, we would measure the photon in state $|0\rangle$ with probability $(1/\sqrt2)^2 = 1/2$ and in state $|1\rangle$ with probability $(1/\sqrt2)^2 = 1/2$ 
- at this point, **the photon is in a superposition of state $|0\rangle$ and $|1\rangle$**, being in both states with the **amplitudes** $1/\sqrt2$ and $1/\sqrt2$ respectively
- if we do not measure which state the photon is in, immediately after it passes through the first beam splitter, then its state remains $\frac{1}{\sqrt2}\begin{bmatrix} 1 \\ 1\end{bmatrix}$ 
- if the photon is allowed to pass through the second beam splitter (before making any measurement of the photon's state), its new state vector becomes$$\begin{bmatrix}\frac{1}{\sqrt2} & \frac{1}{\sqrt2} \\\frac{1}{\sqrt2} & -\frac{1}{\sqrt2}\end{bmatrix}[\frac{1}{\sqrt2}\begin{bmatrix} 1 \\ 1\end{bmatrix}] = \begin{bmatrix} \frac{1}{2} + \frac{1}{2} \\ \frac{1}{2} - \frac{1}{2}\end{bmatrix} = \begin{bmatrix} 1 \\ 0\end{bmatrix} = 1\begin{bmatrix} 1 \\ 0\end{bmatrix} + 0\begin{bmatrix} 0 \\ 1\end{bmatrix}$$
- the amplitude of the state $|0\rangle$ becomes $1$, but the amplitude of the state $|1\rangle$ becomes 0, because the amplitudes of finding the photon in the state $|1\rangle$ cancel each other out. We call this effect **interference**
	- the photon was in **both states** at the same time with certain amplitudes. After passing through the second beam splitter, the "outcomes" are interfered with each other. **The interference can be constructive or destructive**
	- if we measure the state of the photon after the second beam splitter, we find it coming out in the state $|0\rangle$ with probability $1$. Thus, after the second beam splitter the photon is entirely in the state $|0\rangle$, **which is what we observed in the experiments**
	- in the language of quantum mechanics, the second beam splitter **has caused the two states (in superposition) to interfere**, resulting in cancellation of the $|1\rangle$ state