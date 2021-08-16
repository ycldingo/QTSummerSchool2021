# Investigating IBMQ's Hardware with Microwaves
The IBMQ's quantum computer is based on the structure of transmon, which is actually a multi-level system instead of a perfect two-level.
The lowest two energy states, ground state and the first excited state, are used to form the computational basis $\\{ |0\rangle, |1\rangle \\}$ that play an essential role in computing.
In order to focus on these two levels, we need to properly control the applied microwave and prevent the population (information) leakage to the higher energy states.
*Qiskit Pulse* provides a way to modify the external pulse of a quantum device independent of the specific hardware implement.
In this topic, we will explore the hardware via [qiskit.pulse](https://qiskit.org/documentation/apidoc/pulse.html) and run a sequence of experiments virtually, including
1. Find the second energy level and ontain the value of anharmonicity, discuss the fundamental control conditions for superconducting qubits.
2. Measure the elementary parameters of a real device such as decay rates, qubit coherence and coupling strength with the introduction to Janyes-Cummings model.

## Channels (`qiskit.pulse.channels`)
The backend which executes our programs is responsible for mapping the virtual channels to the proper physical channel within the quantum control hardware.
1. ```DriveChannel```: Drive channels transmit gate operation signal.
2. ```MeasureChannel```: Measure channels transmit measurement pulse for readout.
3. ```AcquireChannel```: Acquire channels are used to collect data.
4. ```ControlChannel```: Control channels provides supplementary control to the drive channel.
5. ```RegisterSlot```: Classical registers
6. ```MemorySlot```: Memory slots represent classical memory storage.

## Schedules (```qiskit.pulse.Schedule```)
Schedules are Pulse programs. They describe instruction sequences for the control hardware.
A quantum program *schedule* with exact time constraints for its instructions, operating over all input signal *channels* and supporting special syntaxes for building.
1. Append an instruction to ```sched1```
```
sched1 = Schedule()
sched1 += Play(Gaussian(160, 0.1, 40), DriveChannel(0))
```
2. Append an instruction to ```sched2``` shifted in time by a given amount
```
sched2 = Schedule()
sched2 += Play(Gaussian(160, 0.1, 40), DriveChannel(0)) << 30
```
3. Merge two schedules ```sched1``` and ```sched2```
```
sched2 = sched1 | sched2
```
