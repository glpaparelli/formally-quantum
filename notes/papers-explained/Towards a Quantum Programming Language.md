Summary, comment and explanation of [this](https://www.mathstat.dal.ca/~selinger/papers/papers/qpl.pdf). 

## Introduction
Quantum Computation is traditionally studied at hardware level: either in terms of [[Quantum Gate]]s and [[The Circuit Model of Computation|Circuits]] or in term of quantum Turing machines. 
The former viewpoint emphasizes data

flow and neglects control flow. On the other hand, quantum turing machines can express bot data flow and control flow, but in a sense that is sometimes considered too general to be a suitable foundation for implementations of future quantum computers. 

Our approach is to investigate quantum computation from the point of view of programming languages. 
We propose a view of quantum computation which is able to express both data flow and control flow, while non relying on any particular hardware model. 
This approach can be summarized by the slogan **"quantum data, classical control"**. 
Thus, the data which is manipulated by the programs may involve quantum [[Quantum Mechanics Phenomenas#Superposition|superpositions]], but the control state of a program is classical: there is no "quantum branching" and no notion of executing a quantum superposition of two different statements. 

The programming language presented is **functional**, in the sense that each (atomic or composed) statement operates by transforming a specific set of inputs to outputs. 
This is in contrast to **imperative** programming language, which operate by updating global variables.
Our language is also **statically** typed, which implies that the well-formedness of a program can be checked at compile time. For instance, the principle of non-duplication of quantum data, known as the [[Quantum Mechanics Phenomenas#No-Cloning|no-cloning]] property, is enforced by the syntax of our language. 
In the proposed language we know that any well-typed program is free of runtime errors. 

The language also provides high-level control features such as loops and recursion, and it can accommodate structured data types such as lists or trees. 

The most important feature of the proposed language is that it admits a **denotational semantics**. 
This is achieved by assigning a certain kind of [[Linear Operator]], called a **superoperator**, to each program fragment. 
For the semantics of loops and recursion we use the fact that the superoperators of each given type form a CPO. 
The proposed semantic is **fully abstract** in the sense that two programs fragments are denotationally equivalent if and only if they are indistinguishable in the context of any larger program. 

While the semantics of our quantum programming language can (and will) be described without reference to any particular hardware model, it helps the intuition of a particular hardware device on which the language can be implemented. 
We use the **QRAM** machine, which is a general-purpose classical computer which controls a special quantum hardware device.
The quantum device provides a potentially large number of individually addressable [[Qubit]]s. 
This qubits can be manipulated via two fundamental operations: 
1. [[Unitary Operator]] ([[Linear Transformation]])
2. [[3rd Postulate - Quantum Measurement|measurements]]

In quantum complexity theory, algorithms are often presented in a certain normal form: a quantum computation consists of an initialization, followed by a unitary transformation, followed by a single final measurement; just before the classical result of the algorithm is read. 


