Summary, comment and explanation of [this](https://www.mathstat.dal.ca/~selinger/papers/papers/qpl.pdf). 
## Introduction
Quantum Computation is traditionally studied at hardware level: either in terms of [[Quantum Gate]]s and [[The Circuit Model of Computation|Circuits]] or in term of Quantum Turing Machines. 
The former viewpoint emphasizes data flow and neglects control flow. 
On the other hand, quantum Turing machines can express both data flow and control flow, but in a sense that is sometimes considered too general to be a suitable foundation for implementations of future quantum computers. 

**Our approach is to investigate quantum computation from the point of view of programming languages.** 
We propose a view of quantum computation which is able to express both data flow and control flow, while non relying on any particular hardware model. 
This approach can be summarized by the slogan **"quantum data, classical control"**. 
Thus, the data which is manipulated by the programs may involve quantum [[Quantum Mechanics Phenomenas#Superposition|superpositions]], but the control state of a program is classical: there is no "quantum branching" and no notion of executing a quantum superposition of two different statements. 

The programming language presented is **functional**, in the sense that each (atomic or composed) statement operates by transforming a specific set of inputs to outputs.
This is in contrast to **imperative** programming language, which operate by updating global variables.
Our language is also **statically** typed, which implies that the well-formedness of a program can be checked at compile time. 
For instance, the principle of non-duplication of quantum data, known as the [[Quantum Mechanics Phenomenas#No-Cloning|no-cloning]] property, is enforced by the syntax of our language. 
In the proposed language we know that any well-typed program is free of runtime errors. 

The language also provides high-level control features such as loops and recursion, and it can accommodate structured data types such as lists or trees. 

The most important feature of the proposed language is that it admits a **denotational semantics**. 
This is achieved by assigning a certain kind of [[Linear Transformation]], called a **super-operator**, to each program fragment. 
For the semantics of loops and recursion we use the fact that the super-operators of each given type form a CPO. 
The proposed semantic is **fully abstract** in the sense that two programs fragments are denotationally equivalent if and only if they are indistinguishable in the context of any larger program (remember the compositionality principle)

While the semantics of our quantum programming language can (and will) be described without reference to any particular hardware model, it helps the intuition of a particular hardware device on which the language can be implemented. 
We use the **QRAM** machine, which is a general-purpose classical computer which controls a special quantum hardware device.
The quantum device provides a potentially large number of individually addressable [[Qubit]]s. 
These qubits can be manipulated via two fundamental operations: 
1. [[Unitary Transformation on QC]]s
2. [[Measurement]]s

In quantum complexity theory, algorithms are often presented in a certain normal form. 
A quantum computation consists of: 
- initialization
- unitary transformation
- single final measurement
- read the classical result
## Preliminaries
- [[Horizontal-Vertical Concatenation]]
- [[Qubit#Towards a QPL|Quantum Bits]]
- [[Quantum States]]
- [[Quantum Register]]
- [[Unitary Matrix]]
- [[Hermitian Operator#Hermitian Matrix|Hermitian Matrices]]
- [[Positive Operator#Positive Matrix|Positive Matrices]]
- [[Pure Matrix|Pure Matrices]]
- [[Tensor Product#Special Cases|Tensor Product: Special Cases]]
- [[Unitary Transformation on QC]]s
- [[Measurement]]s
- [[Density Matrix#Density Matrix|Density Matrices]]
- [[Quantum Operations on Density Matrices]]
- [[CPO of Density Matrices]]
### Indexing Convention 
Consider the quantum state $q = \alpha|00\rangle + \beta|01\rangle + \gamma|10\rangle + \delta|11\rangle$. 
By identifying the basis vectors $|00\rangle, |01\rangle, |10\rangle, |11\rangle$ with the [[Computational Basis]] of $\mathbb{C}^4$, we can write the state $q$ as the column (coordinate) vector $$|q\rangle = \begin{bmatrix}\alpha\\\beta\\\gamma\\\delta\end{bmatrix}$$**Here the ordering of the basis vectors is relevant.** 
In general we need an indexing convention which determines how the basis vectors  $|b_1\dots b_n\rangle$ are to be identified with the canonical basis vectors of $\mathbb{C}^{2^n}$. 
In $\mathbb{C}^{4}$ the basis vectors are, as stated before, $\{|00\rangle, |01\rangle, |10\rangle, |11\rangle\}$. 
We identify vectors using a sequence of bits: the sequence $00$ identifies the vector $$|00\rangle = \begin{bmatrix}1\\0\\0\\0\end{bmatrix}$$
###### Convention 3.1
> **Lexicographic Convention**
	Consider the set of bit vectors of length $n$, i.e., tuples $(b_1, b_2,\ \dots,\ b_n)$, where each $b_i \in \{0,1\}$.
	We identify each bit vector with the number $i \in [0, 2^{n-1}]$ of which it is the binary representation (there are $2^n$ possible bit vectors, every possible combination of $0$ and $1$). 
	We also identify the "ket" $|b_1b_2\dots b_n\rangle$ with the $i-th$ canonical basis vector of $\mathbb{C}^{2^n}$ 

**Note that this convention is equivalent to saying that the bit vectors shall always be ordered lexicographically when they are used to index the rows or the columns of some vector or matrix.** 

Sometimes we need to consider a permutation of quantum bits, such as exchanging the 1st and the 2nd qubit in a sequence. 
This induces a corresponding permutation of states. 
More precisely, any permutation of $n$ elements $\phi:\{1,\ \dots,\ n\}\rightarrow \{1,\ \dots,\ n\}$ induces a permutation $2^\phi$ of the set of bit vectors of length $n$, which is defined by $2^\phi(x_1,\ \dots,\ x_n) = (x_{\phi^{-1}(1)},\ \dots,\ x_{\phi^{-1}(n)})$, for $x_1,\ \dots,\ x_n \in \{0, 1\}$. 
Note that this definition is **covariant**, in sense that $2^\phi \circ 2^\psi = 2^{\phi\circ\psi}$. 
As an illustration, consider the permutation $\phi$ such that $\phi(1) = 2,\ \phi(2) = 3,\ \phi(3) = 1$. 
Then $2^\phi(b_1,b_2,b_3) = (b_3, b_1, b_2)$, thus $2^\phi$ maps $000\rightarrow 000,\ 100\rightarrow 010,\ 110\rightarrow 011$ and so forth 
## Quantum Flow Charts
How can we design a quantum programming language and how we can define its semantics? 
**The first problem is to define the syntax.** 
We choose to represent programs as **flow charts**, also known as **control flow diagrams**.
However ours flow charts have a more functional "flavor": in our settings commands act by transforming specific inputs to outputs rather than by updating a global variable. 
Thus we combine the language of control flow with some elements of data flow. 
### Classical Flow Charts 
The concept of "functional style" flow charts is given by examples.
Consider the following classic flow chart: 
**Figure 1** ![[flow-chart-1.png | center | 450]]
Unless indicated by the arrows, the flow is top to bottom. 

Each edge is labelled with a typing judgment, i.e., by a list of typed vars. 
These are the variables which are available at that given point in the program.
For now we only consider the type **bit** of a classical bit (aka Booleans). 
In Figure 1 no variables are created or disposed of, so each edge is labelled with the same typing judgment. 

This program fragment takes a pair of bits, performs a conditional branching and some updates, and then outputs the pair $(b,c)$. 
The semantics of the program can be described by the following map: $$\begin{align}
00 \rightarrow 00\\
01 \rightarrow 01 \\
10 \rightarrow 00 \\
11 \rightarrow 10 
\end{align}$$The **state of the program** between instructions is given by the pair $(e, \rho)$ where $e$ is an edge of a flow chart (basically the **program counter**) and $\rho$ is an assignment of values to the variables with which $e$ is labelled. 
**An important observation is that the two components of the state, instruction pointer and value assignment, are fundamentally of the same nature.**
Thus the instruction pointer could be thought as a variable. 
Conversely the content of a boolean variable can be thought of as encoding a choice between two alternative control paths. 
For example, an edge labeled with a boolean variable $b$ can be replaced by two parallel (unlabeled) edges, corresponding to the states $b=0$ and $b=1$. 
Similarly an edge labelled with two boolean variables can be replaced with four parallel edges.
**In this way each classical flow charts can be transformed into an equivalent (though much larger) flow chart that uses no variables.** 
After such transformation each conditional branch has a predetermined outcome, and each assignment corresponds to a jump to the appropriate parallel component. 

The transformation of the Figure 1 is here shown: 
**Figure 2:**![[flow-chart-2.png | center | 500]]Here the four entrance points of the expanded program correspond to the four possible pairs of boolean inputs of the original program and the four exit points corresponds to the four possible potential pairs of boolean outputs. 

It is the fact that a control edge labelled with a tuple of classical variables can be replaced by a number of parallel control edges that let us say that "control is classical". 
We will see later a similar observation does not apply to quantum data: quantum data is of a fundamentally different nature.
### Probabilistic View of Classical Flow Charts
Consider again the expanded flow chart of Figure 2. 
This time imagine that one of the four entrance points $00,01,10,11$ is selected randomly, with probabilities $A,B,C,D$. 
Then we can annotate, in a top-down fashion, each edge in the flow chart with the probability that this edge will be reached. 
In particular any edge that is unreachable is annotated with $0$. 
The resulting annotation is as follows
**Figure 2**: ![[flow-chart-2.png | center | 500]]The exit points are annotated with the probability of being taken: the probability to have a certain output. 
In this way each program gives rise to a function from tuples of input probabilities to tuples of output probabilities. 
In our example, this function is $$F(A,B,C,D) = (A+C, B, D, 0)$$Note that our original reading of a flow chart as a function from input to output is completely subsumed by this probabilistic view. For instance the fact that $11\rightarrow 10$ is recovered from the fact that $F(0,0,0,1)=(0,0,1,0)$. 

**In practice** it is preferrable to think of a small number of variables rather than of a large number of control paths. 
Therefore we will continue to to draw flow charts in the style of Figure 1.
However the discussion of probabilities still applies, with one modification: each edge that is labelled with $n$ boolean variables should be annotated by a tuple of $2^n$ probabilities, and not by just a single probability ($n$ bits, $2^n$ possible combinations, each one of them with a probability to occur) 
### Summary of Classical Flow Charts Components
The basic operations for boolean flow charts are summarized by the Figure 3.

$\Gamma$ denotes an arbitrary typing context and $A, B$ denotes tuples of probabilities with sum at most $1$.
If $A$ and $B$ are tuples of equal length we use the notation $(A,B)$ to denote the concatenation of $A$ and $B$. 

We distinguish between the **label** of an edge and its **annotation**. 
- **label:** a typing context, part of the syntax of our flow charts language 
	- $\Gamma$ is a label
- **annotation:** a tuple of probabilities, part of the semantics of the language 
	- $A, (A, B)$ and such are annotations
**We use the symbol $=$ to separate labels from annotations.**

Thus, in the following Figure 3 are defined both syntax and semantics of the language. 
Note that the statement of the rules makes use of the indexing convention, because the order of the probabilities in each tuple is determined by the lexicographical ordering of the corresponding states. 
**Figure 3:**![[flow-chart-3.png | center | 700]]
We discuss the never encountered before components:
- **Allocate:** probability $A$ of being there, create new bit and I assign it $0$, therefore to a single bit correspond a $2^1 = 2$ tuple, where the probability of being $0$ is $A$ and the probability of being $1$ is $0$ (to the new bit we assigned $0$, so it is obvious that it has value $1$ with probability $0$)
- **Assignment:** we have a bit $b$ which it has the probability tuple $(A,B)$. We then assign $b:=0$, then the probability of $b$ of being $0$ becomes $A+B$ and the probability of being $1$ becomes $0$
- **Discard bit:** we have a bit $b$ which has probability tuple $(A, B)$. We discard it and we continue with probability $\Gamma$ 
- **Branching bit:** same reasoning, bit $B$ has value $0$ with probability $A$ and $1$ with probability $B$, after the branching the probability of being what we have seen is the summed probability of being $0$ and $1$
- **Merge:** the left edge is taken with probability $A$ and the right edge is traversed with probability $B$, the probability of the merged edge being taken is $A+B$
- **Initial:** creates an unreachable control path (used in Figure 2)
- **Permutation:** Dummy operation that allows us to rearrange the variables in the current typing context

Naturally we will allow various kinds of syntactic sugar in writing flow charts that are not directly covered by the rules in Figure 3. 
For instance, an assignment of the form $b:=c$ can be regarded as an abbreviation for the following conditional assignment:![[flow-chart-4.png | center | 600]](This is more an optimization than sugar but ok)
### Quantum Flow Charts
Quantum flow charts are similar to classical flow charts, except that we add a new type **qbit** of [[Qubit|Quantum Bits]] and two new operations: [[Unitary Transformation on QC]] and [[Measurement]]s. 
A unitary transformation operates on one or more quantum bits; we write $$q \doteq S$$for the operation applying a unitary [[Quantum Gate]] $S$ to the quantum bit $q$.
Note that this operation updates $q$; the notation in analogous to the notation $b:=1$ for classical assignment. 
For the application of a binary quantum gate $S$ to a pair $p,q$ of quantum bits we use the notation $$p,q\doteq S$$and so forth for gates of higher arity. 

Sometimes we also use special notations: 
- $q\  \oplus= 1$ for $q \doteq N$ 
- $q\ \oplus=p$ for $p,q \doteq N_c$, where $N$ and $N_c$ are the [[Pauli Gates - X, Y, Z#NOT Gate|NOT Gate]] and [[CNOT Gate]] gate, respectively. 

The second new operation, the [[Measurement]], is a branching statement since it can have two possible outcomes. 

As a first example we consider following the flow chart
**Figure 4a:**![[flow-chart-5.png | center | 220]]
This program fragment inputs two qubits $p,q$, measure $p$ and then performs one of two possible unitary transformations depending on the outcome of the measurement.
The output is the modified pair $p,q$. 

The behavior of a quantum flow chart can be described as a function from inputs to outputs. 
For instance, in the Figure 4a we have that: 
- the input $|00\rangle$ leads to the output $|01\rangle$
- the input $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|01\rangle$ leads to the output $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|01\rangle$ ([[4th Postulate - Composition of Systems#Entangled States|entangled qubits]])

However, due to the non-probabilistic nature of measurement the output is not always a [[Quantum States|pure state]]: for example the input $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|01\rangle$ will lead to the output $|00\rangle$ or $|01\rangle$ with equal probability. 
We can represent this outcome with the mixed state $\frac{1}{2}\{|00\rangle\} + \frac{1}{2}\{|01\rangle\}$. 

As the example shows, the output of a quantum flow chart is in general a mixed state (and we may take the input to be a mixed state as well). 
Thus, **the semantics of a quantum flow chart is given as a function from mixed states to mixed states.**
To calculate this function we use the [[Density Matrix]] notation and we assume that the input to the program is some mixed state  ![[flow-chart-6.png | center | 250]]where each of $A, B, C, D$ is a $2\times 2$ matrix. 
Remember the indexing convention: the rows and columns of $M$ are indexed by the basic states $00, 01,10,11$ in this respective order. 

For example, if the input mixed state is $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|01\rangle$ then $$M = \begin{bmatrix}\frac{1}{\sqrt2}\\0 \\0\\0\end{bmatrix}\begin{bmatrix}\frac{1}{\sqrt2}&0&0&0\end{bmatrix} + \begin{bmatrix}0 \\\frac{1}{\sqrt2} \\0\\0\end{bmatrix}\begin{bmatrix}0&\frac{1}{\sqrt2}&0&0\end{bmatrix} = \begin{bmatrix}\frac{1}{2} & 0 & 0 & 0\\ 0 & \frac{1}{2} & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0\end{bmatrix}$$Notice that the mixed state $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|01\rangle$ is actually $\frac{1}{\sqrt2}|00\rangle + \frac{1}{\sqrt2}|01\rangle + 0|10\rangle + 0|11\rangle$ 

**Remember:** A mixed state $\lambda_1\{u_1\}+\dots+\lambda_n\{u_n\}$ is simply represented as a linear combination of the density matrices of its pure components, i.e., as $\lambda_1\mathbf{u}_1\mathbf{u}_1^\top + \dots + \lambda_n\mathbf{u}_n\mathbf{u}_n^\top$. 

We can now decorate the flow chart in top-down fashion, by annotating each edge with the mixed state the program is in when it reaches that edge. 
The result is **Figure 4b:**![[imgs/flow-chart-7.png| center | 500]]([[Quantum Operations on Density Matrices]])

The semantics of the entire program fragment is thus given by the following function of density matrices: 
![[flow-chart-8.png| center | 400]]
Note that we followed the usual convention of normalizing all density matrices so that their trace equals the probability that the corresponding edge is reached. 
This convention has several properties: 
- the annotation on each edge is a linear function of the input, in particular the merge operation  amounts to a simple matrix addition
- the traces of the matrices along any horizontal section of the flow chart add up to 1 (assuming that the trace of the input matrix is 1)

Another observation about the program in Figure 4 is that if the input is a pure state, then the states along each of the two branches of the measurement continue to be pure. 
[[Unitary Transformation]]s also preserve [[Quantum States|pure states]]. 
It is finally the merge operation, denoted by a small circle $\circ$ which combines two pure states into an impure state. 
Thus the source of impure states in a quantum system is not the measurement operation but rather the merge operation, i.e., the erasure of classical information.
#### Summary of Quantum Flow Charts Operations 
The operations for basic quantum flow charts are summarized in the following **FIgure 5:**![[flow-chart-9.png| center | 700]]
As before we distinguish between label of an edge and its annotation. 
The label is a typing context $\Gamma$ and it is part of the syntax, the annotation is the density matrix and it is part of the semantics. 

Quantum Bits can be allocated and discarded and here it is understood that allocating a quantum bit means to request an unused qubit from the operating system. 
Such newly allocated quantum bits are assumed to be initialized to $|0\rangle$.
### Combining Classical Data with Quantum Data
TODO