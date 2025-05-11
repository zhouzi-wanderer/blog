---
title: Quantum Information (to be updated)
published: 2025-04-11
description: some notes about quantum information
image: ''
tags: 
  - notes
  - quantum information
category: Notes
draft: false
lang: en
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

    >e.g. NAND gate:
    >|                    Form                    |     Type     |
    >| :----------------------------------------: | :----------: |
    >|         $(a,b)\to\neg(a\wedge b)$          | irreversible |
    >| $(a,b,c)\to(a,b,c\oplus a\wedge b)$, $c=1$ |  reversible  |

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

+ Quantum states: Quantum states of $N$ qubits can be expressed as a vector in a space of dimension $2^N$.An orthonormal basis for the space can be labeled by binary strings such as

  $$
  |\underbrace{0110\cdots10}_{N}\rangle.
  $$

  A general normalized vector can be expanded in this basis as

  $$
  |\psi\rangle=\sum_{x=0}^{2^N-1}a_x|x\rangle,
  $$

  where $a_x$'s are complex number satisfying $\sum_x |a_x|^2=1$. If we measure all N qubits by projecting each onto the $\{|0\rangle,|1\rangle\}$ basis, the probability of obtaining the outcome $|x\rangle$ is $|a_x|^2$.

+ Quantum gate: Apply a unitary transformation U to the N qubits,

  $$
  |\psi\rangle\to U|\psi\rangle.
  $$    

+ Nonelocal correlation: If we divide a quantum system into some subsystems and carry out each measurement within one of the subsystems, which means no collective measurements spanning the boundaries between the subsystems is allowed, the measurements will reveal very little information about what the state of original system is. 
  
  Most of the information is stored in correlations. By measuring the correlations, which is considered to be a “collective” measurement, we can learn much more; in principle, we can completely reconstruct the state.

### 1.5 Quantum parallelism

+ There is a function that transforms input $x$ into output $f(x)$. If we input $N$ bit, there are $2^N$ possible arguments.
  
  To obtain all possible outcomes, $2^N$ computations are required for classical bits; however, only a single calculation is required for qubits.

  >e.g. Deutsch's problem
  >
  >There is a black box that computes a function that takes a single bit $x$ to a single bit $f(x)$. We want to know whether $f(x)$ is constant $(f(0)=f(1))$ or balanced $(f(0)\neq f(1))$.
  >
  >For classical bits, 2 computations are required to get the answer. In contrast, for qubits, it just once calculation suffices.
  >
  >All we need is a transformation $U_f$ that operates on two qubits:
  >$$
  >U_f:|x\rangle|y\rangle\to|x\rangle|y\oplus f(x)\rangle.
  >$$
  >We can choose the second qubit of the input state to be a superposition of $|0\rangle$ and $|1\rangle$, $\frac{1}{\sqrt{2}}(|0\rangle-|1\rangle)$, then
  >$$
  >\begin{align*}
  >U_f:|x\rangle\frac{1}{\sqrt{2}}(|0\rangle-|1\rangle)&\to|x\rangle\frac{1}{\sqrt{2}}(|0\oplus f(x)\rangle-|1\oplus f(x)\rangle)\\
  >&=|x\rangle(-1)^{f(x)}\frac{1}{\sqrt{2}}(|0\rangle-|1\rangle),
  >\end{align*}
  >$$
  >Now suppose we prepare the first qubit as $\frac{1}{\sqrt{2}}(|0\rangle+|1\rangle)$. Then the black box acts as
  >$$
  >\begin{align*}
  >U_f:&\frac{1}{\sqrt{2}}(|0\rangle+|1\rangle)\frac{1}{\sqrt{2}}(|0\rangle-|1\rangle)\to\\
  >&\frac{1}{\sqrt{2}}\left[(-1)^{f(0)}|0\rangle+(-1)^{f(1)}|1\rangle\right]\frac{1}{\sqrt{2}}(|0\rangle-|1\rangle).
  >\end{align*}
  >$$
  >Finally, we can perform a measurement that projects the first qubit onto the basis
  >$$
  >|\pm\rangle=\frac{1}{\sqrt{2}}(|0\rangle\pm|1\rangle).
  >$$
  >Evidently, we will always obtain $|+\rangle$ if the function is constant$(f(0)=f(1))$, and $|-\rangle$ if the function is balanced$(f(0)\ne f(1))$.

+ Let the quantum computer acts as

  $$
  U_f:|x\rangle|\rangle\to|x\rangle|f(x)\rangle,
  $$

  we could choose the input register to be in a state
  $$
  \left[\frac{1}{\sqrt{2}}(|0\rangle+|1\rangle)\right]^N=\frac{1}{2^{N/2}}\sum_{x=0}^{2^N-1}|x\rangle,
  $$

  and by computing f (x) only once, we can generate a state

  $$
  \frac{1}{2^{N/2}}\sum_{x=0}^{2^N-1}|x\rangle|f(x)\rangle.
  $$

  If we measure the first qubit and obtain $|x_0\rangle$. This procedure would prepare a state
  $$
  |x_0\rangle|f(x_0)\rangle.
  $$
  
  By measuring the state, we can find the value of $f(x_0)$. However, we can't determine $f(y_0)$ for any $y_0\ne x_0.$ We need to go back to the step before we measured the first qubit and expect measurement result of first qubit is $y_0$. In this case, then, the quantum computation provided no advantage over a classical one.

### 1.6 A new classification of complexity

## Chap 2 &nbsp;&nbsp;&nbsp;&nbsp;States and Ensembles [📖](https://www.preskill.caltech.edu/ph219/chap2_15.pdf)