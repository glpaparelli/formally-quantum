The [[Quantum Gate]] AND can be made [[The Circuit Model of Computation#Reversible Circuits|Reversible]] by adding additional input wire and two additional output wires: 
![[rev-AND.png | center | 500]]
The reversible AND gate **keeps a copy of the inputs** and XORs the AND of $x_0$ and $x_1$ to the value of the additional input $x_2$.
By setting the additional input bit to $0$ and discarding the copies of the input variables $x_0$ and $x_1$ we can simulate the non-reversible AND. 

The reversible AND gate called the **Toffoli gate** and it flips the third bit if and only if the first two bits are both $1$ (and does nothing otherwise). 

We know that any classical irreversible circuit can be transformed into an equivalent reversible circuit, but: 
- the reversible version might introduce some constant number of additional wires for each gate
- if we have an irreversible classical circuit with depth $T$ and space $S$ we can construct a reversible version that uses a total of $O(S + ST)$ space and depth $T$