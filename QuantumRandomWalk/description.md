# Quantum Random Walk on IBM's Quantum Computers
Quantuum random walk is [first studied since 1993](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.48.1687)
and has been applied in variety of research areas. 
Here we plan to demo a standard one-dimensional discrete-time quantum random via IBM Quantum Experience platform. 
The whole system contains two elements, coin and shift operators, with respect to different registers, and are defined in two subspaces: coin $\mathcal{H}_c$, position $\mathcal{H}_p$. 
Students will learn the concepts of Hilbert space, how the initial state (of coin) influences the outcoming state, as well as the method to expanding the basic model to a higher dimensional case. 

In this topic, we will 
1. Build up the programming script on (1)classical and (2)quantum random walks, and compare the resultant outcome probability distributions for the walker's final position. The Python script will be run on both simulator and real devices.
2. Discuss about the possible applicatioins on quantum random walks.


# Fundamental Background

## Basic elements of random walks

There are two essential elements for random walks, regardless of their version:
- Coin: The coin operation $\mathcal{C}$ determines the direction of the walker. For example, if a 1D case is in consideration, the coin is two-sided, corresponding to the forward $|R\rangle$ and backward $|L\rangle$ shifting options.  A common choice for this $2\times2$ coin is a Hadamard coin

$$
\mathcal{C}
:=H=
\begin{pmatrix}
1 & 1\newline
1 & -1
\end{pmatrix}.
$$

- Shift: The conditional shift operation $\mathcal{S}$ will shift the walker according to its coin state. The operator is given by

$$
\mathcal{S}
:=
\displaystyle\sum_n
|R\rangle \langle R| \otimes |n+1\rangle \langle n|
+
|L\rangle \langle L| \otimes |n-1\rangle \langle n|.
$$

Therefore, the time evolution of the walker will be a combination of the coin and the shift.
For the quantum random walk, the propagator reads
$$
\mathcal{U} = \mathcal{S} \mathcal{C}.
$$
Please be noticed that the order of the two operators cannot be switched, i.e., they are not commutable: $[\mathcal{S}, \mathcal{C}] \neq 0$.



