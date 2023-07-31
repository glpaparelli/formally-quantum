Summary, comment and explanation of [this]([Floyd--hoare logic for quantum programs | ACM Transactions on Programming Languages and Systems](https://dl.acm.org/doi/10.1145/2049706.2049708)). 
We use the [[Dirac Notation]] to represent vectors.

## Introduction
TODO like [[Towards a Quantum Programming Language]]

## Preliminaries
TODO like [[Towards a Quantum Programming Language]]
#### Tensor Product of Hilbert Spaces
**todo: organize better**
In this section we recall the definition of [[Tensor Product]] of a family $\{\mathcal{H}_i\}$ of [[Hilbert Space]]s. 
It is assumed that the set of quantum variables is [[Countably Infinite]], and the type of each quantum variable is either boolean or integer. 
Thus we only need to consider a finite or countably infinite family $\{\mathcal{H}_i\}$ where each $\mathcal{H}_i$ is finite-dimensional or countably infinite-dimensional. 
A more general notion of tensor product should be adopted in order to generalize the results of the article to the case of more quantum variables and other data types. 

Let $\{|\psi_{ij_i}\rangle\}$ be an orthonormal basis of $\mathcal{H}_i$ for each $i$. 
We write $\mathcal{B}$ for the set of tensor products of basis vectors of all $\mathcal{H}_i$; that is $$\mathcal{B} = \{\bigotimes_i|\psi_{ij_i}\rangle\}$$Then $\mathcal{B}$ is a finite or countably infinite set. 
We only consider the case that $\mathcal{B}$ is infinite, since the case of finite $\mathcal{B}$ is simpler. 

Now $\mathcal{B}$ can be written in the form of a sequence of vectors: $$B=\{|\varphi_n\rangle:n=0,1,\dots\}$$
The tensor product of $\mathcal{H}_i$ is defined to be the Hilbert space spanned by $\mathcal{B}$, that is $$\bigotimes_i\mathcal{H}_i = \{\Sigma_n|\varphi_n\rangle:\alpha_n\in \mathbb{C}\ \text{for all}\ n\geq0\ \text{and}\ \Sigma_n|\alpha_n|^2 < \infty \}$$And we define the inner product in $\bigotimes_i \mathcal{H}_i$ as follows:$$(\Sigma_n\alpha_n|\psi_n\rangle, \Sigma_n\alpha'_n|\psi_n\rangle) = \Sigma_n\alpha_n^*\alpha_n'$$for any $\alpha_n, \alpha_n' \in \mathbb{C}, n \geq 0$. 

The notion of partial trace is very useful for the description of a subsystem of a composite quantum system. Let $\mathcal{H}$ and $\mathcal{K}$ be two Hilbert spaces and an operator $A\in \mathcal{L}(\mathcal{H}\bigotimes\mathcal{K})$. 
Then the partial [[Trace]] of $A$ on $\mathcal{H}$ is defined as $$tr_k(A)=\Sigma_i(I_\mathcal{H}\bigotimes\langle\psi_i|)A(I_\mathcal{H}\bigotimes|\psi_i\rangle)$$which is an operator on $\mathcal{H}$, where $\{\psi_i\}$ is an [[Orthonormal Basis]] of $\mathcal{K}$. It can be shown that $tr_k(A)$ does not depend on the choice of $\{\psi_i\}$. 
In particular, if $\mathcal{H}_1$ and $\mathcal{H}_2$ are the state spaces of quantum systems $q_1$ and $q_2$, respectively, and the state of their composite system $q_1q_2$ is described by a [[Density Operator]] $\rho \in \mathcal{D}^{-}(\mathcal{H_1}\bigotimes\mathcal{H_2})$, then $tr_\mathcal{H_2}(\rho)$ is the description for the state of component system  $q_1$. 



## Syntax of Quantum Programs
We assume a [[Countably Infinite]] set $Var$ of **quantum variables**. 

### Quantum Variables
**Quantum Variables:** we use the symbols $q, q', q'', q_0, q_1,\ \dots$ as metavariables ranging over quantum variables, 
In classical computation the **type of a variable** is the **domain of the variable:** the set of all the possible values that a variable could be. 
In quantum computation a **type should be the state space of a quantum system denoted by some quantum variable.**
> Formally a type $t$ is a name of a [[Hilbert Space]] $\mathcal{H}_t$ 

In this article there are only two types: 
- Boolean
- Integer

**The Hilbert spaces denoted by Boolean and Integer are:**$$\begin{align}\mathcal{H}_{boolean}=\mathcal{H}_2 \\ \mathcal{H}_{integer} = \mathcal{H}_\infty\end{align}$$The sets denoted by types Boolean and Integer in classical computation are the [[Computational Basis]] of $\mathcal{H}_{boolean}$ and $\mathcal{H}_{integer}$
- computational basis for $\mathcal{H}_{boolean} = \mathcal{H}_2 = \{|0\rangle, |1\rangle\}$
- computational basis for $\mathcal{H}_{integer} = \mathcal{H}_\infty = \{|n\rangle : n \in \mathbb{Z}\}$ 

**The type of a quantum variable is a Hilbert space and a quantum variable is a vector in that space**.
A variable is a quantum system, according to the [[1st Postulate - State Space]] a quantum system is described by a Hilbert space, and the state of the system is described by a unitary vector.

Assume that each quantum variable $q$ has a type $type(q)$, which is either Boolean or Integer. 
The state space $\mathcal{H}_q$ of a quantum variable $q$ is the Hilbert space denoted by its type: $$\mathcal{H}_q = \mathcal{H}_{type(q)}$$
### Quantum Register 
**A [[Quantum Register]] is a finite sequence of distinct quantum variable.** 
The state space of a quantum register $\bar{q}=q_1,\ \dots, \ q_n$ is the [[Tensor Product]] of the state spaces of the quantum variables occurring in $\bar{q}$ $$\mathcal{H}_\bar{q}=\bigotimes_{i=1}^n\mathcal{H}_{q_i}$$
### Syntax
The quantum programs considered are an extension of classical **while**-programs. 
Formally they are generated by this grammar: 
$$S::= \textbf{skip}\ |\ q:=0\ |\ \bar{q}:=U\bar{q}\ |\ S_1;S_2\ |\ \textbf{measure}\ M[\bar{q}]:\bar{S}\ |\ \textbf{while}\ M[\bar{q}]=1\ \text{do}\ S$$
where:
- $q$ is a quantum variable and $\bar{q}$ is a quantum register
- $U$ in the statement $\bar{q}:=U\bar{q}$ is a [[Unitary Operator]] on $\mathcal{H}_\bar{q}$. 
  In particular, if $type(q)=$ Integer, then the statement $q:=U_{+k}q$, where $U_{+k}$ is the [[K-Translation Operator]], will be often abbreviated to $q=q+k$
- in the statement $\textbf{meausre}\ M[\bar{q}]:\bar{S}$, we have that $M=\{M_m\}$ is a [[3rd Postulate - Quantum Measurement| Quantum Measurement]] on the state space $\mathcal{H}_\bar{q}$ of $\bar{q}$, and $\bar{S}= \{S_m\}$ is a set of quantum programs such that each outcome $m$ of measurement $M$ corresponds to $S_m$
- $M = \{M_0, M_1\}$ in the statement $\textbf{while}\ M[\bar{q}]= 1\ \textbf{do}\ S$ is a yes-no measurement on $\mathcal{H}_\bar{q}$ 

In applications, the [[Unitary Operator]] and measurements in quantum programs are usually chosen from a specific set  which is (approximately) universal; for example, if a program only contains quantum variables of type Boolean, then the unitary operators can be taken from the standard set of [[Universal Quantum Gates]], consisting of the [[Hadamard Gate]], the [[Phase Gate]], the [[CNOT Gate]] and the [[T Gate]], and we only need the measurement in the [[Computational Basis]]. 
For simplicity of the presentation we do not specify there unitary operators and measurements because choosing them does not make any essential difference in the theory developed in this article. 

The symbol $\equiv$ is used to denote **syntactic equality** of quantum programs. 

**Definition 3.1:** the set $var(S)$ of quantum variables in quantum program $S$ is recursively defined as follows: 
1. if $S \equiv\ \textbf{skip}$ then $var(S) = \emptyset$ 
2. if $S \equiv q:=0$ then $var(S) = \{q\}$
3. if $S \equiv \bar{q} := U\bar{q}$ then $var(S) = \{\bar{q}\}$
4. if $S \equiv S_1;S_2$ then $var(S) = var(S_1)\cup var(S_2)$ 
5. if $S \equiv \textbf{measure}\ M[\bar{q}]:\bar{S}$ then $var(S) = \{\bar{q}\}\ \cup\ \bigcup_m var(S_m)$ 
6. if $S \equiv \textbf{while}\ M[\bar{q}]=1\ \textbf{do}\ S$ then $var(S) = \{\bar{q}\} \cup var(S)$ 

# TODO!!
## Operational Semantics of Quantum Programs
We write $\mathcal{H}_{\text{all}}$ for the [[Tensor Product]] of the state space of all quantum variables; that is $$\mathcal{H}_{\text{all}}= \bigotimes_{\text{all q}}\mathcal{H}_q$$
**notation:** $E$ denote the empty quantum program.

A **quantum configuration** is a pair $\langle S, \rho\rangle$ where: 
- $S$ is a quantum program (or the empty quantum program $E$)
- $\rho \in \mathcal{D}^-(\mathcal{H}_\text{all})$ is a [[Density Operator#Partial Density Operator]] on $\mathcal{H}_\text{all}$ and it is used to indicate the (global) state of quantum variables. 
	- $\rho$ is a matrix that describes the quantum state of a physical system, in this case it describe the state of the system made of all the quantum variables
	- semantically speaking we can see it as an **environment**

Let $\bar{q} = q_1,\ \dots,\ q_n$ be a quantum register. A [[Linear Operator]] $\mathcal{A}$ on $\mathcal{H}_\bar{q}$ has a [[Cylinder Extension]] $$A \bigotimes I_{\text{Var} / \{\bar{q}\}}\mathcal{H}_{q} \ \ \ \ \ \ \ \ (1)$$on $\mathcal{H}_{\text{all}}$, where $I_{\text{Var} / \{\bar{q}\}}$ is the identity operator on the Hilbert Space $\bigotimes_{q \in var/{\bar{q}}} \mathcal{H}_q$  
In the sequel we simply write $A$ for its extension $(1)$. 

The **operational semantics of a quantum program** is defined as a transition relation $\rightarrow$ between quantum configurations. 
By a transition $$\langle S,\rho\rangle \rightarrow \langle S',\rho'\rangle$$we mean that after executing quantum program S, one step in state $\rho$, the state of quantum variables become $\rho'$ and $S'$ is the reminder of $S$ still to be executed. 
In particular, if $S' \equiv E$, then $S$ terminates in state $\rho'$. 

The transition relation $\rightarrow$ is given by the following transition rules: 
![[transition-rules.png | center | 650]]

#### Transition Rules
##### Skip
The statement $\textbf{skip}$ does nothing and terminates immediately

##### Initialization
The **initialization** $q:=0$ sets the quantum variable $q$ to the basis state $|0\rangle$. 
In the rule (Initialization) and in the sequel we use $|\varphi\rangle_q$ to indicate the state $|\varphi\rangle$ of the system denoted by the quantum variable $q$. 
**reminder:** each quantum variable is its own quantum system with its own Hilbert Space. 

Thus, for any state $|\varphi\rangle, |\psi\rangle$ of the $q$ system, we can define an operator $|\varphi\rangle_q\langle\psi|$ on the state space of the $q$ system, as follows $$(|\varphi\rangle_q\langle\psi|)|\varphi'\rangle_q = \langle\psi|\varphi'\rangle|\varphi\rangle_q$$**Said easy:** we can define a [[Linear Operator]] using the [[Matrix Representation]] by doing the [[Outer Product]] of $|\varphi\rangle_q\langle\psi|$ and we use it on $|\varphi'\rangle$. 
Computing this linear operator is equal to calculating the [[Inner Product]] $\langle\psi|\varphi'\rangle$ and use the obtained scalar to do the scalar multiplication with $|\varphi\rangle_q$  
**QUESTION:** WHAT IT IS COMPUTED?

Similarly we can define $|\varphi\rangle_\bar{q}$ and $|\varphi\rangle_\bar{q}\langle\psi|$ when $\bar{q}$ is a quantum register and $|\varphi\rangle$ and $|\psi\rangle$ are states in $\mathcal{H}_\bar{q}$. 

Let's consider an example in the case of $type(q) = \textbf{Integer}$. 
First we examine a special case where $\rho$ is a [[Pure State]] 