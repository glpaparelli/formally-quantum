A complex number is an element of a number system that extends the real numbers with a specific element denoted $i$, called the **imaginary unit** and satisfying the equation $i^2 = -1$

Every complex number can be expressed in the **Cartesian form** $a + ib$, where $a$ and $b$ are real numbers. 

A real number $a$ can be regarded as a complex number $a + 0i$ whose imaginary part is zero. 
A purely imaginary number $bi$ is a complex number $0 + bi$, whose real part is zero. 
![[complex-1.png | center | 400]]
Remember that the **absolute value** of a real number $a\in\mathbb{R}$ denotes its distance from the origin. 
So $|a| = \sqrt{a^2}$ denotes the number of units we need to traverse in order to get to the point $O$ (the origin of the axis, either we start from a negative or a positive point). 

Similarly for complex numbers we have that$|a+ib|= \sqrt{a^2 + b^2}$.
The distance we have to traverse to get to the point zero ($0 + i0$) is the **norm** of the two dimensional representation in the reals $(a,b)$ 

It is also known that for $c_1, c_2 \in \mathbb{C}$ holds:
- $|c_1| \times |c_2| = |c_1 \times c_2|$
- $|c_1 + c_2| <= |c_1| + |c_2|$

Every complex number $z = a + ib \in \mathbb{C}$ has its **complex conjugate** $z^* = a -ib \in \mathbb{C}$.   

### Modulus and Argument 
An alternative option for coordinates in the complex plane is the polar coordinate system that uses the distance from the point $z$ to the origin $O$, and the angle subtended between the positive real axis and the segment $Oz$ in a counterclockwise sense. 

This leads to the **polar form** or a complex number:
$$z = x + iy = re^{i\varphi} = r(\cos\varphi + i\sin\varphi)$$
where $r$ is the **absolute value** of $z$, and $\varphi$ is the **argument** of $z$, and we know that: 
- $r = |z| = \sqrt{x^2 + y^2}$
- $\varphi = \arctan\frac{y}{x}$ 
![[complex-2.png | center | 350]]
If $z$ is a real number (if $y = 0$), then $r = |x|$, said simple: the absolute value of a real number equals to its absolute value as a complex number. 