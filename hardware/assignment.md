# Assignment 1: NOT Gate with Open Pulse
Please create an experiment to excite the qubit from the ground state via [Open Pulse](https://qiskit.org/documentation/apidoc/pulse.html) feature. We will start from searching for the proper driving pulse frequency to its amplitude. Execute the experiment on a real device and analyze the measurement outcome. Do you obtain 100% of $|1\rangle$ ? Why?
In additional to constructing the driving pulse step-by-step, we can evaluate the theoretical $\pi$-pulse for a qubit directly from the viewpoint of flipping a qubit.
The modified pulse for IBM's superconducting qubit will definitely look different to that of a perfect two-level system. 
Please compare the measurement results for the two pulses and discuss about the difference.



# Assignment 2: 1-2 Transition for a Superconducting Qubit
Please find the 1-2 transition frequency  $f_{12}$  of a real device, and calculate the difference between  $f_{01}$  and  $f_{12}$ . This frequency difference is defined as the anharmonicity  $\alpha$  of the quantum system:
$$ \alpha := \omega_{01} - \omega_{12}, $$
where $\omega = 2\pi f$. Is $\alpha$ positive or negative? If you further explore the higher energy levels, you are may find out that these levels follow a relation
$$ \begin{cases}
\omega_{01} - \omega_{12} = \alpha \newline
\omega_{01} - \omega_{23} = 2\alpha \newline
\vdots
\end{cases}, $$
that is,
$$ \begin{cases}
\omega_1 - \omega_0 = \omega_{01} \newline
\omega_2 - \omega_1 = \omega_{01} + \alpha \newline
\omega_3 - \omega_2 = \omega_{01} + 2 \alpha \newline
\vdots
\omega_n - \omega_{n-1} = \omega_{01} + (n-1) \alpha \newline
\end{cases}. $$
For different physical implement of quantum computers, both sign and the value of the anharmonicity are different. After finishing the exercise, please check your result with the [official document](https://quantum-computing.ibm.com/services?services=systems).
