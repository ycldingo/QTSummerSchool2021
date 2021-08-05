# Investigating IBMQ's Hardware with Microwaves
The IBMQ's quantum computer is based on the structure of transmon, which is actually a multi-level system instead of a perfect two-level.
The lowest two energy states, ground state and the first excited state, are used to form the computational basis $\left\{ |0\rangle, |1\rangle \right\}$ that play an essential role in computing.
In order to focus on these two levels, we need to properly control the applied microwave and prevent the population (information) leakage to the higher energy states.
*Qiskit Pulse* provides a way to modify the external pulse of a quantum device independent of the specific hardware implement.
In this topic, we will explore the hardware via this promising language and run a sequence of experiments virtually, including
1. Find the second energy level and ontain the value of anharmonicity, discuss the fundamental control conditions for superconducting qubits.
2. Measure the elementary parameters of a real device such as decay rates and coupling strength with the introduction to Janyes-Cummings model.
