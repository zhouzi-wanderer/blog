---
title: Quantum Information (to be updated)
published: 2025-04-11
description: 'some notes about quantum information'
image: ''
tags: [notes, quantum information]
category: 'Notes'
draft: false
lang: 'en'
---

<style>
p {
  line-height: 1.5;
}
</style>

# Quantum information

>This notes refer to the lecture notes of [Professor John Preskill](https://www.preskill.caltech.edu/)  
>To get the original lecture notes, click 📖

## Chap 1 &nbsp;&nbsp;&nbsp;&nbsp;Introduction and Overview [📖](https://www.preskill.caltech.edu/ph229/notes/chap1.pdf)

### 1.1 Physics of information

+ Landauer's principle: Erasing 1 bit information requires at lease work $W=kT\ln2$.

+ Reversible computation: The information is fully retained, that is, the input and output correspond one to one to avoid erasing information and energy cost.

    e.g. NAND gate:

    |                    Form                    |     Type     |
    | :----------------------------------------: | :----------: |
    |         $(a,b)\to\neg(a\wedge b)$          | irreversible |
    | $(a,b,c)\to(a,b,c\oplus a\wedge b)$, $c=1$ |  reversible  |

+ Maxwell's demon: Information entropy.

### 1.2 Quantum information

+ True randomness

+ Uncertainty principle

+ Acquiring information causes disturbance

+ No-cloning principle

+ Nonlocal correlation

### 1.3 Efficient quantum algorithms

+ Quantum bits have some properties that classical bits don't have, which can reduce the computational complexity on specific problems.

### 1.4 Quantum complexity

+ Quantum states: Quantum states of N qubits can be expressed as a vector in a space of dimension $2^N$.An orthonormal basis for the space can be labeled by binary strings such as

    $$
    |\underbrace{0110\cdots10}_{N}\rangle
    $$

    A general normalized vector can be expanded in this basis as

    $$
    |\psi\rangle=\sum_{x=0}^{2^N-1} a_x|x\rangle
    $$

    where $a_x$'s are complex number satisfying $\sum_x |a_x|^2=1$. If we measure all N qubits by projecting each onto the $\{|0\rangle,|1\rangle\}$ basis, the probability of obtaining the outcome $|x\rangle$ is $|a_x|^2$.

+ Quantum gate: Apply a unitary transformation U to the N qubits,

    $$
    |\psi\rangle\to U|\psi\rangle
    $$    

+ Nonelocal correlation: If we divide a quantum system into some subsystems and carry out each measurement within one of the subsystems, which means no collective measurements spanning the boundaries between the subsystems is allowed, the measurements will reveal very little information about what the state of original system is. 
  
  Most of the information is stored in correlations. By measuring the correlations, which is considered to be a “collective” measurement, we can learn much more; in principle, we can completely reconstruct the state.

### 1.5 Quantum parallelism

## Chap 2 &nbsp;&nbsp;&nbsp;&nbsp;States and Ensembles [📖](https://www.preskill.caltech.edu/ph219/chap2_15.pdf)