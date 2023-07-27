The Bloch sphere is a **geometrical representation and visualization** of a qubit in a 3D space. 

Many operations on **single** [[Qubit]] can be neatly described within the Bloch sphere.
Mind that there is no simple generalization of the Bloch sphere known for multiple qubits. 

We know that a qubit is expressed as $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ and hence there are **four real numbers involved in the qubit:** $Re(\alpha), Im(\alpha), Re(\beta), Im(\beta)$.
But, as it turns out, there are **only two degrees of freedom:**

**1)** we express the state $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ in polar coordinates and obtain$$\begin{align}\alpha = r_\alpha e^{i\varphi\alpha}  = r_\alpha (\cos\varphi_\alpha + i\sin\varphi_\alpha), \ \ \ r_\alpha = |\alpha|\\\beta = r_\beta e^{i\varphi\beta}  = r_\beta (\cos\varphi_\beta + i\sin\varphi_\beta), \ \ \ r_\beta = |\beta|\end{align}$$
and we get $$|\psi\rangle = r_\alpha e^{i\varphi\alpha}|0\rangle + r_\beta e^{i\varphi\beta}|1\rangle, \ \ \ r_\alpha, \varphi_\alpha, r_\beta, \varphi_\beta \in \mathbb{R}$$
**2)** multiplying the state by a global phase factor, an arbitrary complex number of norm $1$, has no observable consequences

**3)** we multiply the state by $e^{-i\varphi\alpha}$ and obtain an equivalent expression for the qubit, where the amplitude for $|0\rangle$ is real $$\begin{align}|\psi\rangle = r_\alpha e^{i\varphi\alpha}|0\rangle + r_\beta e^{i\varphi\beta}|1\rangle \equiv \\e^{-i\varphi\alpha}(r_\alpha e^{i\varphi\alpha}|0\rangle + r_\beta e^{i\varphi\beta}|1\rangle) = \\ r_\alpha|0\rangle+ r_\beta e^{i(\varphi_\beta - \varphi_\alpha)}|1\rangle =\\ r_\alpha|0\rangle + r_\beta e^{i\varphi}|1\rangle \end{align}$$**4)** now we only have three real parameters: $$r_\alpha, r_\beta, \varphi = \varphi_\beta - \varphi_\alpha \   \text{with}\  r_\alpha, r_\beta \in [0,1], \ 0 \leq \varphi \leq 2\pi$$the physical properties of the qubit stay unchanged: 
- the absolute values of the amplitudes remain unchanged $r_\alpha, r_\beta$, and therefore the probability to measure the qubit in the corresponding basis state does not change
- the difference between the phases of $\alpha$ and $\beta$ does not change: $\varphi_\alpha - \varphi_\beta$ 

**5)** we use the normalization constraint $|\alpha|^2 + |\beta|^2 = r^2_\alpha+ r^2_\beta = 1, \ \ \ r_\alpha, r_\beta \in [0,1]$ and we rewrite $r_\alpha$ and $r_\beta$ as follows: $$r_\alpha = cos(\rho), \ \ \ r_1 = \sin(\rho)$$the angle $\rho$ that describes the relation between $r_\alpha$ and $r_\beta$ lies between $0$ and $\pi/2$ 
   ![[bloch-sphere-2.png | center | 250]]
and we get $$|\psi\rangle = \cos(\rho)|0\rangle + \sin(\rho)e^{i\varphi}|1\rangle$$
where we have **only two real parameters**, $\rho \in [0, \pi/2]$ and $\varphi \in [0, 2\pi]$ 

**6)** we set $$\rho = \theta/2, \ \ \ 0 \leq \theta \leq \pi$$and we finally get $$|\psi\rangle = \cos(\theta/2)|0\rangle + \sin(\theta/2)e^{i\varphi}|1\rangle$$where: 
   - $||\psi||_2 = 1$
   - $\varphi = \varphi_\beta - \varphi_a\alpha, \ \ \ 0 \leq \varphi \leq 2\pi$
   - $\theta = 2\cos^{-1}r_\alpha, \ \ \ 0 \leq \theta \leq \pi$
![[bloch-sphere-3.png | center | 350]]
**note:** we cannot use $\theta$, instead of $\theta/2$ in the state vector $|\psi\rangle$. In fact, in this case the points $(\theta, \varphi)$ and $(\pi - \theta, \varphi - \pi)$ would represent the same qubit, up to the phase factor $-1$: the parametrization would map the same qubit twice, on the upper hemisphere and on the lower one.
To mitigate this problem we divide $\theta$ by two (i.e., we double the "latitude")

**In summary:** two real parameters $\theta$ and $\varphi$ are sufficient to describe the state vector of a qubit (since state vectors are constrained to have norm $1$ and are equivalent up to global phase). 
These two angles can be used to define a point on the three-dimensional sphere of $\mathbb{R}^3$ of radius $1$, the Bloch sphere.
There is a **biunivocal correspondence** between qubits and **points on the Bloch sphere:** every point on the Bloch sphere corresponds to a unique state.

**Two angles correspond to the longitude and the latitude needed to specify any position on the sphere:** 
- $\theta$ is equivalent to the geometrical **latitude** on the sphere: it is angle that $|\psi\rangle$ makes with the $z$ axis
- $\varphi$ is equivalent to the **longitude**: the angle between the projection of $|\psi\rangle$ on the plane $(x,y)$ and the $x$ axis
![[bloch-sphere-4.png | center | 400]]
The **north pole** corresponds to the state $|0\rangle$ and the **south pole** corresponds to the state $|1\rangle$.
When a qubit is measured in the standard basis it collapses to a bit, or equivalently to the north or south pole of the Bloch sphere. 
The angle $\theta$ is the latitude of the qubit and controls the chance of collapsing north or south: the closer is the position to one of the poles, the greater the chance of finding the qubit in the basis corresponding to that pole. 
If the qubit is on the equator, there is a 50-50 chance of it collapsing in either $|0\rangle$ or $|1\rangle$. 