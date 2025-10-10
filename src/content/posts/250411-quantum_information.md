---
title: Quantum Information
published: 2025-04-11
description: 'This note refers to the lecture notes of Professor John Preskill.'
image: '../../assets/covers/studying.png'
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

>This note refers to the lecture notes of [Professor John Preskill](https://www.preskill.caltech.edu/).   
>To get the original lecture notes, click [📖]().

# Chap 1 &nbsp;&nbsp;&nbsp;&nbsp;Introduction and Overview [📖](https://www.preskill.caltech.edu/ph229/notes/chap1.pdf)

## 1.1 Physics of information

+ Landauer's principle: Erasing 1 bit information requires at lease work $W=kT\ln2$.

+ Reversible computation: The information is fully retained, that is, the input and output correspond one to one to avoid erasing information and energy cost.

    >e.g. NAND gate:
    >|                    Form                    |     Type     |
    >| :----------------------------------------: | :----------: |
    >|         $(a,b)\to\neg(a\wedge b)$          | irreversible |
    >| $(a,b,c)\to(a,b,c\oplus a\wedge b)$, $c=1$ |  reversible  |

+ Maxwell's demon: Information entropy.

## 1.2 Quantum information

+ True randomness

+ Uncertainty principle

+ Acquiring information causes disturbance

+ No-cloning principle

+ Nonlocal correlation

## 1.3 Efficient quantum algorithms

+ Quantum bits have some properties that classical bits don't have, which can reduce the computational complexity on [specific problems].

## 1.4 Quantum complexity

+ Quantum states: Quantum states of $N$ qubits can be expressed as a vector in a space of dimension $2^N$.An orthonormal basis for the space can be labeled by binary strings such as

  $$
  \ket{\underbrace{ 0110 \cdots 10}_{N}}.
  $$

  A general normalized vector can be expanded in this basis as

  $$
  \ket \psi = \sum_{x=0}^{2^N-1} a_x \ket x,
  $$

  where $a_x$'s are complex number satisfying $\sum_x |a_x|^2=1$. If we measure all N qubits by projecting each onto the $\{\ket 0,\ket 1\}$ basis, the probability of obtaining the outcome $\ket x$ is $|a_x|^2$.

+ Quantum gate: Apply a unitary transformation U to the N qubits,

  $$
  \ket \psi \to U \ket \psi.
  $$    

+ Nonelocal correlation: If we divide a quantum system into some subsystems and carry out each measurement within one of the subsystems, which means no collective measurements spanning the boundaries between the subsystems is allowed, the measurements will reveal very little information about what the state of original system is. 
  
  Most of the information is stored in correlations. By measuring the correlations, which is considered to be a “collective” measurement, we can learn much more; in principle, we can completely reconstruct the state.

## 1.5 Quantum parallelism

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
  >U_f:\ket x \ket y \to \ket x \ket{y \oplus f(x)}.
  >$$
  >We can choose the second qubit of the input state to be a superposition of $\ket 0$ and $\ket 1$, $\frac{1}{\sqrt{2}}(\ket 0-\ket 1)$, then
  >$$
  >\begin{align*}
  >U_f:\ket x \frac{1}{\sqrt{2}}(\ket 0 - \ket 1) & \to \ket x \frac{1}{\sqrt{2}}(\ket{0 \oplus f(x)} - \ket{1 \oplus f(x)})\\
  >&=\ket x(-1)^{f(x)} \frac{1}{\sqrt{2}}(\ket 0-\ket 1),
  >\end{align*}
  >$$
  >Now suppose we prepare the first qubit as $\frac{1}{\sqrt{2}}(\ket 0+\ket 1)$. Then the black box acts as
  >$$
  >\begin{align*}
  >U_f:& \frac{1}{\sqrt{2}}(\ket 0+\ket 1) \frac{1}{\sqrt{2}}(\ket 0-\ket 1) \to\\
  >& \frac{1}{\sqrt{2}} \left[(-1)^{f(0)} \ket 0+(-1)^{f(1)}\ket 1 \right] \frac{1}{\sqrt{2}}(\ket 0-\ket 1).
  >\end{align*}
  >$$
  >Finally, we can perform a measurement that projects the first qubit onto the basis
  >$$
  >\ket \pm = \frac{1}{\sqrt{2}}(\ket 0\pm\ket 1).
  >$$
  >Evidently, we will always obtain $|+\rangle$ if the function is constant$(f(0) = f(1))$, and $\ket -$ if the function is balanced$(f(0) \ne f(1))$.

+ Let the quantum computer acts as

  $$
  U_f:\ket x \ket{} \to \ket x \ket{f(x)},
  $$

  we could choose the input register to be in a state
  $$
  \left[\frac{1}{\sqrt{2}}(\ket 0+\ket 1) \right]^N = \frac{1}{2^{N/2}} \sum_{x=0}^{2^N-1} \ket x,
  $$

  and by computing f (x) only once, we can generate a state

  $$
  \frac{1}{2^{N/2}} \sum_{x=0}^{2^N-1} \ket x \ket{f(x)}.
  $$

  If we measure the first qubit and obtain $\ket{x_0}$. This procedure would prepare a state
  $$
  \ket{x_0} \ket{f(x_0)}.
  $$
  
  By measuring the state, we can find the value of $f(x_0)$. However, we can't determine $f(y_0)$ for any $y_0\ne x_0.$ We need to go back to the step before we measured the first qubit and expect measurement result of first qubit is $y_0$. In this case, then, the quantum computation provided no advantage over a classical one.

## 1.6 A new classification of complexity

+ For classical complexity: for any algorithm A and N bits input, $T_A(N)$ is the largest elementary steps needed to take to complete.
  
  Call A is polynomial time if $T_A(N) \le$ Poly($N$), where Poly($N$) denotes a polynomial of $N$. Otherwise, we say it is exponential time.

+ Quantum classification of complexity is indeed different than the classical classification (as is suspected but not proved).

## 1.7 What about errors?

+ Information is encoded in superposition of states $\ket \psi$. Unfortunately, these nonlocal correlations are extremely fragile and tend to decay very rapidly in practice. The problem is that quantum system is inevitably in contact with a much larger system, its environment. Interactions between a quantum system and its environment establish nonlocal correlations between the two. Eventually the quantum information that we initially encoded in the system becomes encoded in correlations between the system and the environment, which means we can no longer access the information by observing only the system, or we can say the information is irrevocably lost.
  
  Even if we could achieve perfect isolation from the environment, we cannot expect quantum computers to operate with perfect accuracy, as quantum gates may introduce certain errors into the system, for example, $U_0 \to U_0(1 + O(\varepsilon))$, through it's small, errors will accumulate.

+ Overall, we can divide the errors into four categories.

  >Phase error: $\ket 0 + \ket 1 \to \ket 0 - \ket 1$.
  >
  >Small error: initial state $a \ket 0 + b \ket 1$ changes amount of order $\varepsilon$.
  >
  >Measurement causes disturbance.
  >
  >No cloning: quantum information cannot be copied with perfect fidelity.

## 1.8 Quantum error-correcting codes

+ Before we talk about quantum error correction, let's look at how does classical error correction work? The simplest example of a classical error-correcting code is a repetition code: we replace the bit we wish to protect by 3 copies of the bit, 

  $$
  0 \to (000),
  $$

  $$
  1 \to (111).
  $$

  With a quantum code, we should be mindful of the requirement that we will need to be able to correct the errors without measuring any of the encoded information.

  Suppose that we encode a single qubit with 3 qubits:

  $$
  \ket{0} \to \ket{\overline{0}} = \ket{000}
  $$

  $$
  \ket{1} \to \ket{\overline{1}} = \ket{111}
  $$

  For a 3-qubit state $\ket{xyz}$ we could measure the two-qubit observables $y \oplus z$, and $x \oplus z$. For both $\ket{xyz} = \ket{000}$ and $\ket{111}$ these would be 0, but if any one bit flips, then at least one of these quantities will be 1. In fact, if there is a single bit flip, the two bits

  $$
  (y \oplus z, x \oplus z),
  $$

  just designate in binary notation the position of the bit that flipped. For example, if the first qubit flips, 

  $$
  \ket{000} \to \ket{100}, \ket{111} \to \ket{011}
  $$

  the measurement of $(y \oplus z, x \oplus z)$ yield the result $(0, 1)$, which instructs us to flip the first bit.

  For small errors, like

  $$
  \ket{000} \to \ket{000} + \varepsilon \ket{100},
  $$

  $$
  \ket{111} \to \ket{111} + \varepsilon \ket{011}.
  $$

  In measuring $(y \oplus z, x \oplus z)$, we would project out an eigenstate of this observable. Most of the time (probability $1 − |\varepsilon|^2$) we obtain the result $(0, 0)$ and project the damaged state back to the original state, and so correct the error. Occasionally (probability $|\varepsilon|^2$) we obtain the result $(0, 1)$ and project the state onto the state that the first qubit is flipped. But then the outcome instructs us to flip the first bit, which restores the original state.

+ To address phase errors, we encode a single qubit using nine qubits, according to

  $$
  \ket{+} \to \ket{\overline{+}} = \frac{1}{2^{3/2}} (\ket{000} + \ket{111})(\ket{000} + \ket{111})(\ket{000} + \ket{111}),
  $$

  $$
  \ket{-} \to \ket{\overline{-}} = \frac{1}{2^{3/2}} (\ket{000} - \ket{111})(\ket{000} - \ket{111})(\ket{000} - \ket{111}).
  $$
  
  Now suppose that a phase flip occurs in one of the clusters
  
  $$
  \ket{000} + \ket{111} \to \ket{000} - \ket{111}
  $$
  
  In this case, we need to measure a six-qubit observable to do the comparison, for example, the observable that flips qubits 1 through 6. A pair of clusters with the same sign is an eigenstate with eigenvalue +1, and a pair of clusters with opposite sign is an eigenstate with eigenvalue −1. By measuring the six-qubit observable for a second pair of clusters, we can determine which cluster has a different sign than the others. For example,

  $$
  \begin{align*}
  & \frac{1}{2^{3/2}} (\ket{000} + \ket{111})(\ket{000} + \ket{111})(\ket{000} + \ket{111}) \\
  \to & \frac{1} {2^{3/2}}(\ket{000} - \ket{111})(\ket{000} + \ket{111})(\ket{000} + \ket{111}),
  \end{align*}
  $$

  by measuring the observable that flips qubits 1 through 6 and the observable that flips qubits 4 through 9, we get the result $(-1, 1)$, , which instructs us to change the sign of first cluster.

## 1.9 Quantum hardware

+ To build hardware for a quantum computer, we’ll need technology that enables us to manipulate qubits. The hardware will need to meet some stringent specifications:

  1. Storage: We’ll need to store qubits for a long time, long enough to complete an interesting computation.
  2. Isolation: The qubits must be well isolated from the environment, to minimize decoherence errors.
  3. Readout: We’ll need to measure the qubits efficiently and reliably.
  4. Gates: We’ll need to manipulate the quantum states of individual qubits, and to induce controlled interactions among qubits, so that we can perform quantum gates.
  5. Precision: The quantum gates should be implemented with high precision if the device is to perform reliably.
   
+ There are many kinds of quantum hardwares, like iron trap, superconducting quantum computer etc. The introduction in the lecture seems outdated. To better understand these things, it is recommended to read relevant reviews from recent years.

# Chap 2 &nbsp;&nbsp;&nbsp;&nbsp;States and Ensembles [📖](https://www.preskill.caltech.edu/ph219/chap2_15.pdf)

## 2.1 Axioms of quantum mechanics

+ Axiom 1. __States__.

  A state is a complete description of a physical system. In quantum mechanics, a state is a ray in a Hilbert space.

+ Axiom 2. __Observables__.

  An observable is a property of a physical system that in principle can be measured. In quantum mechanics, an observable is a self-adjoint operator.

+ Axiom 3. __Measurement__.

  A measurement is a process in which information about the state of a physical system is acquired by an observer. In quantum mechanics, the measurement of an observable $\pmb{A}$ prepares an eigenstate of $\pmb{A}$, and the observer learns the value of the corresponding eigenvalue.If the quantum state just prior to the measurement is $\ket{\psi}$, then the outcome an is obtained with a priori probability

  $$
  \mathrm{Prob}(a_n) = ||\pmb{E_n} \ket{\psi}||^2 = \bra{\psi} \pmb{E_n} \ket{\psi};
  $$
  
  if the outcome $a_n$ is attained, then the (normalized) quantum state just after the measurement is

  $$
  \frac{\pmb{E_n} \ket{\psi}}{||\pmb{E_n} \ket{\psi}||}.
  $$

+ Axiom 4. __Dynamics__.

  Dynamics describes how a state evolves over time. In quantum mechanics, the time evolution of a closed system is described by a unitary operator.

+ Axiom 5. __Composite Systems__.

  If the Hilbert space of system $A$ is $\mathcal{H}_A$ and the Hilbert space of system $B$ is $\mathcal{H}_B$, then the Hilbert space of the composite systems $AB$ is the tensor product $\mathcal{H}_A \otimes \mathcal{H}_B$. If system $A$ is prepared in the state $\ket{\psi}_{A}$ and system B is prepared in the state $\ket{\varphi}_{B}$, then the composite system’s state is the product $\ket{\psi}_A \otimes \ket{\varphi}_B$.

## 2.2 The qubit

