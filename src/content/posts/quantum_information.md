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

# Chap 1 &nbsp;&nbsp;&nbsp; Introduction and Overview [📖](https://www.preskill.caltech.edu/ph229/notes/chap1.pdf)

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

+ Quantum bits have some properties that classical bits don't have, which can reduce the computational complexity on specific problems.

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

&nbsp;

&nbsp;

&nbsp;

# Chap 2 &nbsp;&nbsp;&nbsp; States and Ensembles [📖](https://www.preskill.caltech.edu/ph219/chap2_15.pdf)

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

+ The smallest nontrivial Hilbert space is two-dimensional. We may denote an orthonormal basis for a two-dimensional vector space as $\{\ket{0}, \ket{1}\}$. A qubit is a quantum system described by a two-dimensional Hilbert space, whose state can take any value of the form

  $$
  \ket{\psi} = \alpha \ket{0} + \beta \ket{1},
  $$

  where $\alpha$ and $\beta$ are complex numbers satisfying the normalization condition $|\alpha|^2 + |\beta|^2 = 1$.

### 2.2.1 Spin-1/2

+ $\ket{0}$ and $\ket{1}$ are the spin up ($\ket{\uparrow}$) and spin down ($\ket{\downarrow}$) states along a particular axis such as the z-axis.

  A finite rotation is expressed as (here $\hbar = 1$)

  $$
  \bm{R}(\hat{n}, \theta) = e^{-i \theta \hat{n} \cdot \bm{J}},
  $$
  
  Rotations about distinct axes don’t commute. From elementary properties of rotations, we find the commutation relations

  $$
  [\bm{J_i}, \bm{J_j}] = i \varepsilon_{ijk} \bm{J_k}.
  $$

  where $\varepsilon_{ijk}$ is the totally antisymmetric tensor with $\varepsilon_{123} = 1$, and repeated indices are summed. The operators $\bm{J_i}$ are the generators of rotations. For a spin-1/2 system, the operators $\bm{J_i}$ can be represented by the Pauli matrices:

  $$
  \bm{J_i} = \frac{\bm{\sigma_i}}{2},
  $$

  where

  $$
  \bm{\sigma_1} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, ~~~ \bm{\sigma_2} = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, ~~~ \bm{\sigma_3} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}.
  $$

  It is easy to check that the Pauli matrices satisfy the relations

  $$
  [\bm{\sigma_i}, \bm{\sigma_j}] = 2 i \varepsilon_{ijk} \bm{\sigma_k}, ~~~ \{\bm{\sigma_i}, \bm{\sigma_j}\} = 2 \delta_{ij} \bm{I}.
  $$

  Then we have

  $$
  \bm{\sigma_i} \bm{\sigma_j} = \frac{1}{2} (\{\bm{\sigma_i}, \bm{\sigma_j}\} + [\bm{\sigma_i}, \bm{\sigma_j}]) = \delta_{ij} \bm{I} + i \varepsilon_{ijk} \bm{\sigma_k}.
  $$

  Now consider the dot product of a vector and the Pauli operators

  $$
  \hat{n} \cdot \bm{\sigma} = n_1 \bm{\sigma_1} + n_2 \bm{\sigma_2} + n_3 \bm{\sigma_3} = \begin{pmatrix} n_3 & n_1 - i n_2 \\ n_1 + i n_2 & -n_3 \end{pmatrix},
  $$

  where $\hat{n} = (n_1, n_2, n_3)$ is a unit vector. Then we have

  $$
  (\hat{n} \cdot \bm{\sigma}) (\hat{n} \cdot \bm{\sigma}) = \hat{n}^2 \bm{I} = \bm{I}.
  $$

  By expanding the exponential series, we see that a finite rotation along the axis $\hat{n}$ by an angle $\theta$ is represented as

  $$
  \begin{align*}
  \bm{R}(\hat{n}, \theta) &= \sum_{i=0}^\infty \frac{1}{i!} (-i \hat{n} \cdot \bm{\sigma})^i (\theta/2)^i \\ &= \sum_{i=0}^\infty \frac{1}{(2i)!} (\theta/2)^{2i} + i  \hat{n} \cdot \bm{\sigma} \frac{1}{(2i+1)!} (\theta/2)^{2i+1} \\ &= \cos(\theta/2) - i  \hat{n} \cdot \bm{\sigma}\sin(\theta/2).
  \end{align*}
  $$

  which means that a rotation along the axis $\hat{n}$ by an angle $\theta$ is represented by a unitary operator that is a linear combination of the identity operator and the operator $\hat{n} \cdot \bm{\sigma}$.

  Therefore, we can construct eigenstates of angular momentum along the axis $\hat{n} = (\sin \theta \cos \phi, \sin \theta \sin \phi, \cos \theta)$ as

  $$
  \ket{\hat{n}+} = \bm{R}(\hat{y'}, \theta) \ket{0} = \begin{pmatrix} \cos(\theta/2) \\ e^{i \phi} \sin(\theta/2) \end{pmatrix},\\ \ket{\hat{n}-} = \bm{R}(\hat{y'}, \theta) \ket{1} = \begin{pmatrix} - e^{- i \phi} \sin(\theta/2) \\ \cos(\theta/2) \end{pmatrix},
  $$

  where $\hat{y'} = (-\sin \phi, \cos \phi, 0)$ is a unit vector orthogonal to $\hat{n}$ and $\hat{z}$.

  In order to make the form more symmetrical, we can rewrite the states as

  $$
  \ket{\hat{n'}+} = \bm{R}(\hat{y'}, \theta) \bm{R}(\hat{z}, \phi) \ket{0} = \begin{pmatrix} e^{- i \phi /2} \cos(\theta/2) \\ e^{i \phi /2} \sin(\theta/2) \end{pmatrix},\\ \ket{\hat{n'}-} = \bm{R}(\hat{y'}, \theta) \bm{R}(\hat{z}, \phi) \ket{1} = \begin{pmatrix} - e^{- i \phi /2} \sin(\theta/2) \\ e^{i \phi /2} \cos(\theta/2) \end{pmatrix}.
  $$

  These are two different representations of the same state, differing by at most a phase. The states $\ket{\hat{n}+}$ and $\ket{\hat{n}-}$ are orthonormal eigenstates of the operator $\hat{n} \cdot \bm{\sigma}$ with eigenvalues +1 and −1, respectively.

  In the special case $\theta = \pi/2, \phi = 0$ (the $\hat{x} $-axis), we have

  $$
  \ket{\hat{x}+} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}, ~~~ \ket{\hat{x}-} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix},
  $$

  and for $\theta = \pi/2, \phi = \pi/2$ (the $\hat{y}$-axis), we have

  $$
  \ket{\hat{y}+} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ i \end{pmatrix}, ~~~ \ket{\hat{y}-} = \frac{1}{\sqrt{2}} \begin{pmatrix} i \\ 1 \end{pmatrix}.
  $$

### 2.2.2 Phonon polarization

+ Another important two-state system is provided by a photon, which can have two independent polarizations.

  We can choose the basis states to be the states of horizontal polarization $\ket{H}$ and vertical polarization $\ket{V}$. Under a rotation about the axis of propagation, the two linear polarization states transform as

  $$
  \ket{H} \to \cos \theta \ket{H} + \sin \theta \ket{V}, ~~~ \ket{V} \to -\sin \theta \ket{H} + \cos \theta \ket{V},
  $$

  which can be represented by a $2 \times 2$ rotation matrix

  $$
  \begin{pmatrix} \cos \theta & -\sin \theta \\ \sin \theta & \cos \theta \end{pmatrix}.
  $$

  The matrix has two eigenstates, the states of circular polarization:

  $$
  \ket{R} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ i \end{pmatrix}, ~~~ \ket{L} = \frac{1}{\sqrt{2}} \begin{pmatrix} i \\ 1 \end{pmatrix},
  $$

  with eigenvalues $e^{i\theta}$ and $e^{-i\theta}$, the states of right and left circular polarization. That is, these are the eigenstates of the rotation generator $\sigma_2$ with eigenvalues $\pm 1$. Because the eigenvalues are $\pm 1$ (not $\pm 1/2$) we say that the photon has spin-1.

## 2.3 The density operator

### 2.3.1 The bipartite quantum system

+ Having understood everything about a single qubit, we are ready to address systems with two qubits. Interaction among multiple qubits is essential for quantum computation, and the most distinctive feature of quantum mechanics, nonlocal correlation, arises only in systems with two or more qubits.

  When we study open systems, that is, when we limit our attention to just part of a larger system,  it is generally impossible to assign a single state vector to system $A$ alone. Thus, we must use a different powerful tool, the density operator (which will be introduced later), to describe the state of the system. We will find that (contrary to the axioms):

  >1. States are not rays.  
  > 
  >2. Measurements are not orthogonal projections.  
  > 
  >3. Evolution is not unitary.

  To arrive at the laws obeyed by open quantum systems, we must recall our fifth axiom, which relates the description of a composite quantum system to the description of its component parts. As a first step toward understanding the quantum description of an open system, we consider a bipartite system consisting of two subsystems, $A$ and $B$.

  The Hilbert space of a bipartite system $AB$ is the tensor product $\mathcal{H}_A \otimes \mathcal{H}_B$ of the Hilbert spaces of the two subsystems. We may denote an orthonormal basis for the space as $\{\ket{00}, \ket{01}, \ket{10}, \ket{11}\}$. A general state of the composite system can be expressed as

  $$
  \ket{\psi} = \sum_{i,j} c_{ij} \ket{ij},
  $$

  where $\ket{ij} = \ket{i}_A \otimes \ket{j}_B$ and the complex coefficients $c_{ij}$ satisfy the normalization condition $\sum_{i,j} |c_{ij}|^2 = 1$.

  An observable acting on both qubits A and B, $\bm{M} = \bm{M_A} \otimes \bm{M_B}$, has expectation value

  $$
  \langle \bm{M} \rangle = \bra{\psi} (\bm{M_A} \otimes \bm{M_B}) \ket{\psi} = \text{tr}(\bm{M} \bm{\rho}),
  $$

  where $\bm{\rho} = \ket{\psi} \bra{\psi}$ is the density operator for the composite system.
  
  An observable acting on qubit A only can be expressed as

  $$
  \bm{M_A} \otimes \bm{I_B},
  $$

  where $\bm{M_A}$ is a Hermitian operator acting on $\mathcal{H}_A$, and $\bm{I_B}$ is the identity operator acting on $\mathcal{H}_B$.

  The expectation value of the observable in the state $\ket{\psi}$ is:

  $$
  \begin{align*}
  \langle \bm{M_A} \otimes \bm{I_B} \rangle &= \bra{\psi} (\bm{M_A} \otimes \bm{I_B}) \ket{\psi} \\ &= \sum_{i,j,i',j'} c_{ij}^* c_{i'j'} \bra{ij} (\bm{M_A} \otimes \bm{I_B}) \ket{i'j'} \\ &= \sum_{i,j,i',j'} c_{ij}^* c_{i'j'} \bra{i} \bm{M_A} \ket{i'} \bra{j} \bm{I_B} \ket{j'} \\ &= \sum_{i,i'} \alpha_{ii'} \bra{i} \bm{M_A} \ket{i'} \\ &= \text{tr}(\bm{M_A} \bm{\rho_A}),
  \end{align*}
  $$

  where $\alpha_{ii'} = \sum_{j} c_{ij}^* c_{i'j}$ and $\bm{\rho_A} = \sum_{ii'} \alpha_{ii'} \ket{i'} \bra{i}$. The operator $\bm{\rho_A}$ is called the density operator (or density matrix) for qubit A.

  $\bm{\rho_A}$ can be obtained from $\bm{\rho}$ by taking the partial trace over subsystem B:

  $$
  \bm{\rho_A} = \text{tr}_B(\bm{\rho}) = \sum_{j} (\bm{I_A} \otimes \bra{j}_B) \bm{\rho} (\bm{I_A} \otimes \ket{j}_B) = \sum_{i,j,i'} c_{ij}^* c_{i'j} \ket{i'} \bra{i}.
  $$

  The density operator $\bm{\rho}$ has the following properties:
  1. $\bm{\rho}$ is Hermitian: $\bm{\rho} = \bm{\rho}^\dagger$.
  2. $\bm{\rho}$ is positive: for any vector $\ket{\phi}$, $\bra{\phi} \bm{\rho} \ket{\phi} \ge 0$.
  3. $\bm{\rho}$ has unit trace: $\text{tr}(\bm{\rho}) = 1$.

+ If the state is a pure state $\ket{\psi}$, then the density matrix $\bm{\rho} = \ket{\psi} \bra{\psi}$ is the projection onto the one-dimensional space spanned by $\ket{\psi}$. Otherwise the state is mixed.

  A general density matrix, expressed in the basis {$\ket{i}$} in which it is diagonal, has the form

  $$
  \bm{\rho} = \sum_i p_i \ket{i} \bra{i},
  $$

  where $0 < p_i ≤ 1$ and $\sum_i p_i = 1$. A useful criterion for distinguishing pure states from mixed states is provided by the trace of the square of the density operator. If $\bm{\rho}$ represents a pure state, then $\bm{\rho}^2 = \bm{\rho}$, and so $\text{tr}(\bm{\rho}^2) = \text{tr}(\bm{\rho}) = 1$. On the other hand, if $\bm{\rho}$ represents a mixed state, then $\text{tr}(\bm{\rho}^2) < 1$. Thus we have the criterion

  $$
  \begin{cases}
  \text{tr}(\bm{\rho}^2) = 1 & \text{pure state}\\
  \text{tr}(\bm{\rho}^2) < 1 & \text{mixed state}
  \end{cases}
  $$

  The expectation value of any observable $\bm{M}$ in a state described by the density operator $\bm{\rho}$ is given by

  $$
  \langle \bm{M} \rangle = \text{tr}(\bm{M} \bm{\rho}) = \sum_i p_i \bra{i} \bm{M} \ket{i}.
  $$

### 2.3.2 Bloch sphere

+ Let’s return to the case in which system A is a single qubit, and consider the form of the general density matrix. The most general self-adjoint 2 × 2 matrix has four real parameters, and can be expanded in the basis {$\bm{I}, \bm{\sigma_1}, \bm{\sigma_2}, \bm{\sigma_3}$}. Since each $\bm{\sigma_i}$ is traceless, the coefficient of $\bm{I}$ in the expansion of a density matrix $\bm{\rho}$ must be $\frac{1}{2}$ (so that $\text{tr}(\bm{\rho}) = 1$), and $\bm{\rho}$ may be expressed as

  $$
  \bm{\rho} = \bm{\rho} (\bm{P}) = \frac{1}{2} (\bm{I} + \bm{P} \cdot \bm{\sigma}) = \frac{1}{2} \begin{pmatrix} 1 + P_3 & P_1 - i P_2 \\ P_1 + i P_2 & 1 - P_3 \end{pmatrix},
  $$

  where $P_1, P_2, P_3$ are real numbers. We can compute $\det \bm{\rho} = \frac{1}{4} (1 - \bm{P}^2)$. Therefore, a necessary condition for $\bm{\rho}$ to have nonnegative eigenvalues is $\det \bm{\rho} \geq 0$ or $\bm{P}^2 \leq 1$. This condition is also sufficient; since $\text{tr} \bm{\rho} = 1$, it is not possible for $\bm{\rho}$ to have two negative eigenvalues.Thus, there is a 1 − 1 correspondence between the possible density matrices of a single qubit and the points on the unit 3-dimensional sphere $0 ≤ |\bm{P}| ≤ 1$. This ball is usually called the Bloch sphere (although it is really a ball, not a sphere).

  The pure states correspond to the points on the surface of the Bloch sphere, where $|\bm{P}| = 1$. The mixed states correspond to the points in the interior of the Bloch sphere, where $|\bm{P}| < 1$. The completely mixed state $\bm{\rho} = \frac{1}{2} \bm{I}$ corresponds to the center of the Bloch sphere, where $\bm{P} = 0$.

  The vector $\bm{P}$ is called the polarization vector or the Bloch vector. The expectation value of the spin operator $\hat{n} \cdot \bm{\sigma}$ in the state $\bm{\rho}$ is

  $$
  \langle \hat{n} \cdot \bm{\sigma} \rangle _{\bm{\rho}} = \text{tr}(\hat{n} \cdot \bm{\sigma} \bm{\rho} (\bm{P})) = \hat{n} \cdot \bm{P}.
  $$

  The following equation is used in the derivation of the above formula

  $$
  \text{tr}(\bm{\sigma_i} \bm{\sigma_j}) = 2 \delta_{ij}.
  $$

## 2.4 Schmidt decomposition

+ A bipartite pure state can be expressed in a standard form (the Schmidt decomposition) that is often very useful.

  Let $\mathcal{H}_A$ and $\mathcal{H}_B$ be the Hilbert spaces of systems $A$ and $B$ with dimensions $d_A$ and $d_B$, respectively. Let $\{\ket{i}_A\}$ and $\{\ket{j}_B\}$ be orthonormal bases for $\mathcal{H}_A$ and $\mathcal{H}_B$. An arbitrary vector in $\mathcal{H}_A \otimes \mathcal{H}_B$ can be expanded as

  $$
  \ket{\psi}_{AB} = \sum_{i} \sum_{j} c_{ij} \ket{i}_A \otimes \ket{j}_B = \sum_{i} \ket{i}_A \otimes \ket{\tilde{i}}_B,
  $$

  where the complex coefficients $c_{ij}$ satisfy the normalization condition $\sum_{i,j} |c_{ij}|^2 = 1$ and $\ket{\tilde{i}}_B = \sum_{j} c_{ij} \ket{j}_B$ are (not necessarily normalized or orthogonal) vectors in $\mathcal{H}_B$.

  If the $\{\ket{i}_A\}$ basis is chosen to be the basis in which $\bm{\rho}_A$ is diagonal, 

  $$
  \bm{\rho}_A = \sum_i p_i \ket{i}_A \bra{i}_A,
  $$

  where $p_i$ are the eigenvalues of $\bm{\rho}_A$ and $\ket{i}_A$ are the corresponding eigenvectors. Also, we can obtain $\bm{\rho}_A$ from $\ket{\psi}$ by taking the partial trace over subsystem B:

  $$
  \bm{\rho}_A = \text{tr}_B(\ket{\psi} \bra{\psi}) = \sum_{i,j,k} \ket{i}_A \bra{j}_A \langle k | \tilde{i} \rangle_B \langle \tilde{j} | k \rangle_B = \sum_{i,j} \ket{i}_A \bra{j}_A \langle \tilde{j} | \tilde{i} \rangle_B,
  $$

  where we have used the completeness relation $\sum_k \ket{k}_B \bra{k}_B = \bm{I}_B$. Comparing the two expressions for $\bm{\rho}_A$, we see that

  $$
  \langle \tilde{j} | \tilde{i} \rangle_B = p_i \delta_{ij},
  $$

  which means that the vectors $\ket{\tilde{i}}_B$ are orthogonal, and their norms are $\sqrt{p_i}$. We obtain orthonormal vectors by rescaling,
  
  $$
  \ket{i}_B = \frac{1}{\sqrt{p_i}} \ket{\tilde{i}}_B,
  $$

  Thus we can express $\ket{\psi}$ as

  $$
  \ket{\psi} = \sum_{i} \sqrt{p_i} \ket{i}_A \otimes \ket{i}_B.
  $$

  The above equation is the Schmidt decomposition of the bipartite pure state $\ket{\psi}_{AB}$. It is instructive to compare the Schmidt decomposition of the bipartite pure state $\ket{\psi}_{AB}$ with its expansion in a generic orthonormal basis

  $$
  \ket{\psi}_{AB} = \sum_{a} \sum_{b} c_{ab} \ket{a}_A \otimes \ket{b}_B.
  $$

  $\ket{a}_A$ and $\ket{b}_B$ are not necessarily eigenstates of their respective density matrices. The coefficients $c_{ab}$ can be regarded as the matrix elements of a $d_A \times d_B$ matrix $C$. By performing a singular value decomposition of the matrix $C$, we can express it as

  $$
  C = U_A \Lambda U_B^T,
  $$

  where $U_A$ is a $d_A \times d_A$ unitary matrix, $U_B$ is a $d_B \times d_B$ unitary matrix, and $\Lambda$ is a $d_A \times d_B$ diagonal matrix with nonnegative real entries. The diagonal entries of $\Lambda$ are called the singular values of $C$. If we define new orthonormal bases for $\mathcal{H}_A$ and $\mathcal{H}_B$ by

  $$
  \ket{i}_A = \sum_{a} (U_A)_{ai} \ket{a}_A, ~~~ \ket{i'}_B = \sum_{b} (U_B)_{bi} \ket{b}_B, ~~~ \Lambda_{ij} = \sqrt{p_i} \delta_{ij},
  $$

  then we can express the state $\ket{\psi}$ in the new bases as

  $$
  \ket{\psi}_{AB} = \sum_{i=1}^{r} \sqrt{p_i} \ket{i}_A \otimes \ket{i}_B,
  $$

  where $\sqrt{p_i}$ are the nonzero singular values of $C$, and $r$ is the rank of the matrix $C$. This expression is called the Schmidt decomposition of the state $\ket{\psi}$.

+ The Schmidt decomposition has several important properties:

  1. The number of nonzero terms in the Schmidt decomposition, $r$, is called the Schmidt rank of the state $\ket{\psi}_{AB}$. The Schmidt rank is at most $\min(d_A, d_B)$.

  2. The reduced density matrices $\bm{\rho_A}$ and $\bm{\rho_B}$ have the same nonzero eigenvalues, which are the squares of the Schmidt coefficients $\sqrt{p_i}$.

  3. The Schmidt decomposition is unique if $\rho_A$ (and hence $\rho_B$) have no degenerate eigenvalues other than zero.

  4. A bipartite pure state $\ket{\psi}_{AB}$ is entangled if and only if its Schmidt rank is greater than 1.

## 2.5 Ensemble

### 2.5.1 Convexity

+ A density operator $\bm{\rho}$ can be expressed as a convex combination of pure states:

  $$
  \bm{\rho} = \sum_i p_i \ket{\psi_i} \bra{\psi_i},
  $$

  where $0 < p_i ≤ 1$ and $\sum_i p_i = 1$. The states {$\ket{\psi_i}$} are all normalized vectors, but we do not assume that they are mutually orthogonal. The set of all density operators is convex, meaning that if $\bm{\rho_1}$ and $\bm{\rho_2}$ are density operators, then any convex combination of them is also a density operator:

  $$
  \bm{\rho} = \lambda \bm{\rho_1} + (1 - \lambda) \bm{\rho_2}, ~~~ 0 ≤ \lambda ≤ 1.
  $$

  The extreme points of this convex set are the pure states, which cannot be expressed as a nontrivial convex combination of other density operators.

### 2.5.2 Ensemble preparation

+ A density operator $\bm{\rho}$ can be prepared by an ensemble of pure states $\{(p_i, \ket{\psi_i})\}$, where $p_i$ is the probability of preparing the pure state $\ket{\psi_i}$. The ensemble preparation can be achieved by a classical random process that selects the state $\ket{\psi_i}$ with probability $p_i$.

  Different ensembles can yield the same density operator. For example, the completely mixed state $\bm{\rho} = \frac{1}{2} \bm{I}$ for a single qubit can be prepared by the ensemble $\{(\frac{1}{2}, \ket{0}), (\frac{1}{2}, \ket{1})\}$
  
  $$
  \bm{\rho} = \frac{1}{2} \ket{0} \bra{0} + \frac{1}{2} \ket{1} \bra{1},
  $$

  or by the ensemble $\{(\frac{1}{2}, \ket{+}), (\frac{1}{2}, \ket{-})\}$,

  $$
  \bm{\rho} = \frac{1}{2} \ket{+} \bra{+} + \frac{1}{2} \ket{-} \bra{-},
  $$

  where $\ket{+} = \frac{1}{\sqrt{2}} (\ket{0} + \ket{1})$ and $\ket{-} = \frac{1}{\sqrt{2}} (\ket{0} - \ket{1})$.

  The non-uniqueness of ensemble preparation reflects the fact that the density operator contains all the information about the statistical properties of the quantum system, but does not specify how the system was prepared.

### 2.5.3 The HJW theorem

+ Any density operator $\bm{\rho}_A$ acting on a Hilbert space $\mathcal{H}_A$ can be represented as the reduced density operator of a pure state $\ket{\Psi}_{AB}$ in a larger Hilbert space $\mathcal{H}_A \otimes \mathcal{H}_B$. This process is called purification.

  To purify a density operator $\bm{\rho}_A$, we can perform the following steps:

  1. For a density matrix $\bm{\rho}_A$, consider one such realization:

     $$
     \bm{\rho}_A = \sum_i q_i \ket{\varphi_i}_A \bra{\varphi_i}_A, ~~~ \sum_i q_i = 1.
     $$

     Here the states {$\ket{\varphi_i}_A$} are all normalized vectors, but we do not assume that they are mutually orthogonal.

  2. Introduce an auxiliary Hilbert space $\mathcal{H}_B$ with an orthonormal basis $\{\ket{\alpha}_B\}$, where the vectors $\{\ket{\alpha}_B\} \in \mathcal{H}_B$ are mutually orthogonal and normalized.

  3. Construct the purified state $\ket{\Psi}_{AB}$ in the composite Hilbert space $\mathcal{H}_A \otimes \mathcal{H}_B$ as follows:

     $$
     \ket{\Psi_1}_{AB} = \sum_i \sqrt{q_i} \ket{\varphi_i}_A \otimes \ket{\alpha_i}_B.
     $$

  The reduced density operator of subsystem A is obtained by taking the partial trace over subsystem B:

  $$
  \bm{\rho}_A = \text{tr}_B(\ket{\Psi_1}_{AB} \bra{\Psi_1}_{AB}) = \sum_i q_i \ket{\varphi_i}_A \bra{\varphi_i}_A.
  $$

+ The purified state $\ket{\Psi_1}_{AB}$ is not unique; any unitary transformation applied to subsystem $B$ will yield a different purified state that still reduces to the same density operator $\bm{\rho}_A$ when traced over $B$. This non-uniqueness reflects the fact that there are many different ways to represent the same mixed state as a pure state in a larger Hilbert space.

  We can realize a different ensemble interpretation of $\bm{\rho}_A$ by performing a different measurement of $B$. So let

  $$
  \bm{\rho}_A = \sum_\mu r_\mu \ket{\phi_\mu}_A \bra{\phi_\mu}_A, ~~~ \sum_\mu r_\mu = 1,
  $$

  be another ensemble interpretation of $\bm{\rho}_A$. Then we can construct another purified state $\ket{\Psi_2}_{AB}$ as follows:

  $$
  \ket{\Psi_2}_{AB} = \sum_\mu \sqrt{r_\mu} \ket{\phi_\mu}_A \otimes \ket{\beta_\mu}_B.
  $$

  where $\{\ket{\beta_\mu}_B\}$ is another orthonormal basis in $\mathcal{H}_B$. $\ket{\Psi_1}_{AB}$ and $\ket{\Psi_2}_{AB}$ are two different purifications of the same density operator $\bm{\rho}_A$. Since they are purifications of the same density operator, we can find their relation by using the Schmidt decomposition. Let

  $$
  \bm{\rho}_A = \sum_i p_i \ket{i}_A \bra{i}_A, ~~~ \sum_i p_i = 1,
  $$

  be the spectral decomposition of $\bm{\rho}_A$. Then we can express $\ket{\Psi_1}_{AB}$ and $\ket{\Psi_2}_{AB}$ in their Schmidt decompositions:

  $$
  \ket{\Psi_1}_{AB} = \sum_i \sqrt{p_i} \ket{i}_A \otimes \ket{i}_B,
  $$

  $$
  \ket{\Psi_2}_{AB} = \sum_i \sqrt{p_i} \ket{i}_A \otimes \ket{i'}_B,
  $$

  where $\{\ket{i}_B\}$ and $\{\ket{i'}_B\}$ are orthonormal bases in $\mathcal{H}_B$. Since both $\{\ket{i}_B\}$ and $\{\ket{i'}_B\}$ are orthonormal bases, there exists a unitary transformation $\bm{U}_B = \sum_{i} \ket{i'}_B \bra{i}_B$ such that

  $$
  \ket{\Psi_2}_{AB} = (\bm{I_A} \otimes \bm{U}_B) \ket{\Psi_1}_{AB}.
  $$

  This result is known as the Hughston-Jozsa-Wootters (HJW) theorem. It shows that any two ensemble interpretations of a given density operator can be related by a suitable unitary transformation on the auxiliary system used in the purification. The HJW theorem has important implications for quantum information theory, as it highlights the flexibility in representing mixed states and the role of auxiliary systems in quantum state preparation and manipulation.

### 2.5.4 Quantum erasure

+ The non-uniqueness of ensemble preparations for a given density matrix, as explained by the HJW theorem, is beautifully illustrated by the phenomenon of quantum erasure. It demonstrates that the information we can potentially acquire about a quantum system dictates its behavior (e.g., whether it exhibits wave-like interference), and that "erasing" this information can restore the seemingly lost quantum effects.

  Let's consider a mixed state for a qubit A, which represents a particle that can take one of two paths, $\ket{0}_A$ or $\ket{1}_A$, with equal probability and no coherence between them:
  $$
  \bm{\rho}_A = \frac{1}{2} \ket{0}\bra{0} + \frac{1}{2} \ket{1}\bra{1} = \frac{1}{2}\bm{I}.
  $$
  This state will not produce an interference pattern because the off-diagonal elements of the density matrix are zero.

  As per the HJW theorem, we can "purify" this state by introducing an auxiliary system B and constructing an entangled pure state $\ket{\Psi}_{AB}$ such that $\text{tr}_B(\ket{\Psi}_{AB}\bra{\Psi}_{AB}) = \bm{\rho}_A$. One such purification is:
  $$
  \ket{\Psi}_{AB} = \frac{1}{\sqrt{2}} (\ket{0}_A \otimes \ket{0}_B + \ket{1}_A \otimes \ket{1}_B).
  $$
  Here, system B acts as a "which-path" detector. If system B is measured in the state $\ket{0}_B$, we know with certainty that system A is in state $\ket{0}_A$ (took path 0). If B is in $\ket{1}_B$, then A is in $\ket{1}_A$ (took path 1). As long as this which-path information exists in system B, system A will not show interference.

  The "erasure" happens when we perform a measurement on system B that makes it impossible to know whether B was in state $\ket{0}_B$ or $\ket{1}_B$. This is achieved by measuring B in a different basis, for example, the Hadamard basis $\{\ket{+}_B, \ket{-}_B\}$, where $\ket{\pm}_B = \frac{1}{\sqrt{2}}(\ket{0}_B \pm \ket{1}_B)$.

  To see the effect on A, we can rewrite the entangled state $\ket{\Psi}_{AB}$ in terms of this new basis for B. By substituting $\ket{0}_B = \frac{1}{\sqrt{2}}(\ket{+}_B + \ket{-}_B)$ and $\ket{1}_B = \frac{1}{\sqrt{2}}(\ket{+}_B - \ket{-}_B)$, we get:
  $$
  \begin{align*}
  \ket{\Psi}_{AB} &= \frac{1}{\sqrt{2}} \left[ \ket{0}_A \otimes \frac{1}{\sqrt{2}}(\ket{+}_B + \ket{-}_B) + \ket{1}_A \otimes \frac{1}{\sqrt{2}}(\ket{+}_B - \ket{-}_B) \right] \\
  &= \frac{1}{2} \left[ (\ket{0}_A + \ket{1}_A) \otimes \ket{+}_B + (\ket{0}_A - \ket{1}_A) \otimes \ket{-}_B \right] \\
  &= \frac{1}{\sqrt{2}} \left[ \ket{+}_A \otimes \ket{+}_B + \ket{-}_A \otimes \ket{-}_B \right]
  \end{align*}
  $$

  Now, if we measure system B and get the result $\ket{+}_B$, the state of system A collapses to the pure state $\ket{+}_A = \frac{1}{\sqrt{2}}(\ket{0}_A + \ket{1}_A)$. This state has maximum coherence between the two paths and will produce a specific interference pattern.

  If we instead measure system B and get the result $\ket{-}_B$, the state of system A collapses to the pure state $\ket{-}_A = \frac{1}{\sqrt{2}}(\ket{0}_A - \ket{1}_A)$. This state will also produce an interference pattern, but one that is phase-shifted relative to the first.

  By measuring B in the Hadamard basis, we have "erased" the which-path information. We can't tell which path particle A took. In doing so, we can sort the detection events of A based on the measurement outcomes of B. The sub-ensemble of A-particles corresponding to the B-measurement $\ket{+}_B$ shows one interference pattern, and the sub-ensemble corresponding to $\ket{-}_B$ shows another. The sum of these two patterns washes out the interference, which is consistent with the initial mixed state $\bm{\rho}_A$. Thus, the interference is "recovered" through correlation, showcasing how different measurements on an auxiliary system can reveal different ensemble interpretations of a density operator.

+ Delayed Choice: The quantum eraser experiment becomes even more profound when considering the "delayed choice" aspect. The decision of which basis to use for measuring system B (the which-path detector) can be made after system A has already been detected. For example, we can let system A hit a screen, recording its position, and only later choose whether to measure system B in the path basis $\{\ket{0}_B, \ket{1}_B\}$ or the erasure basis $\{\ket{+}_B, \ket{-}_B\}$. When we later analyze the data from system A, we sort its detection events according to the subsequent measurement outcomes of B. If we chose the path basis for B, the sorted A-data shows no interference. If we chose the erasure basis for B, the sorted A-data reveals the interference patterns. This implies that the behavior of particle A (whether it acts like a particle or a wave) is not determined until a future measurement is made on its entangled partner B. 

  It is crucial to emphasize that this doesn't mean information travels back in time; rather, it highlights that we cannot attribute a definite classical history to a quantum system before the measurement is fully completed. An observer looking only at the total detection results for system A will **never** see an interference pattern in real-time. The interference fringes only emerge during classical post-processing, when the results from A are correlated with the measurement outcomes from B. Here is why:

  1.  **Two possible outcomes for A**: When we choose to measure B in the erasure basis $\{\ket{+}_B, \ket{-}_B\}$, there are two possible collapsed states for A, each occurring with 50% probability:
  
      * If B is measured as $\ket{+}_B$, system A collapses to $\ket{\psi_+}_A = \frac{1}{\sqrt{2}} (\ket{0}_A + \ket{1}_A)$.
      
      * If B is measured as $\ket{-}_B$, system A collapses to $\ket{\psi_-}_A = \frac{1}{\sqrt{2}} (\ket{0}_A - \ket{1}_A)$.

  2.  **Opposite interference patterns**: Let's denote the wavefunction at a position $x$ on the screen from path 0 and path 1 as $\psi_0(x)$ and $\psi_1(x)$ respectively. The probability distribution (i.e., the interference pattern) for each case is:

      $$
      P(x | +_B) = |\langle x | \psi_+ \rangle_A|^2 = \frac{1}{2} |\psi_0(x) + \psi_1(x)|^2 = \frac{1}{2} (|\psi_0|^2 + |\psi_1|^2 + 2\text{Re}(\psi_0^* \psi_1))
      $$

      $$
      P(x | -_B) = |\langle x | \psi_- \rangle_A|^2 = \frac{1}{2} |\psi_0(x) - \psi_1(x)|^2 = \frac{1}{2} (|\psi_0|^2 + |\psi_1|^2 - 2\text{Re}(\psi_0^* \psi_1))
      $$
      
      Notice the opposite sign of the interference term $2\text{Re}(\psi_0^* \psi_1)$. This means the two patterns are perfectly **out of phase**: the bright fringes of one pattern correspond exactly to the dark fringes of the other.

  3.  **Total pattern washes out**: The observer of A, without knowledge of B's measurement, sees the sum of these two mutually exclusive outcomes, weighted by their probabilities (each 50%):
    
      $$
      \begin{align*}
      P_{\text{total}}(x) &= \frac{1}{2} P(x | +_B) + \frac{1}{2} P(x | -_B) \\
      &= \frac{1}{4} (|\psi_0|^2 + |\psi_1|^2 + 2\text{Re}(\psi_0^* \psi_1)) + \frac{1}{4} (|\psi_0|^2 + |\psi_1|^2 - 2\text{Re}(\psi_0^* \psi_1)) \\
      &= \frac{1}{2} (|\psi_0|^2 + |\psi_1|^2)
      \end{align*}
      $$

  The interference terms cancel perfectly. The resulting total pattern is a featureless distribution, identical to the one described by the mixed state $\bm{\rho}_A = \frac{1}{2}\bm{I}$. The choice made on B only determines which patterns can be retrospectively sorted and revealed from the total, seemingly random data set. This can also explain why faster-than-light communication is impossible using entanglement and quantum erasure. The interference patterns only emerge when the data from both systems are compared after the fact, requiring classical communication.

## 2.6 Distance measures for quantum information

### 2.6.1 Fidelity and Uhlmann’s theorem

+ The distinguishability of two pure states $\ket{\psi}$ and $\ket{\phi}$ is quantified by the deviation from 1 of their overlap $|\langle \phi | \psi \rangle|^2$, also called fidelity. For two density operators $\bm{\rho}$ and $\bm{\sigma}$, the fidelity $F(\bm{\rho}, \bm{\sigma})$ between two density operators $\bm{\rho}$ and $\bm{\sigma}$ is defined as

  $$
  F(\bm{\rho}, \bm{\sigma}) = \left(\text{tr} \sqrt{\bm{\rho^\frac{1}{2}} \bm{\sigma} \bm{\rho^\frac{1}{2}}} \right)^2.
  $$

  The square root of a density operator $\bm{\rho}$, denoted as $\bm{\rho}^{\frac{1}{2}}$ or $\sqrt{\bm{\rho}}$, is a unique positive semidefinite operator that, when multiplied by itself, yields $\bm{\rho}$. The most straightforward way to compute it is through spectral decomposition. If the spectral decomposition of $\bm{\rho}$ is
  
  $$
  \bm{\rho} = \sum_i p_i \ket{i} \bra{i},
  $$
  
  where $p_i$ are the eigenvalues and $\ket{i}$ are the corresponding eigenvectors, then its square root is defined as:

  $$
  \bm{\rho}^{\frac{1}{2}} = \sum_i \sqrt{p_i} \ket{i} \bra{i}.
  $$

  The fidelity has the following properties:

  1. $0 ≤ F(\bm{\rho}, \bm{\sigma}) ≤ 1$.
  2. $F(\bm{\rho}, \bm{\sigma}) = F(\bm{\sigma}, \bm{\rho})$ (symmetry).
  3. $F(\bm{\rho}, \bm{\sigma}) = 1$ if and only if $\bm{\rho} = \bm{\sigma}$.
  4. If $\bm{\rho} = \ket{\psi} \bra{\psi}$ is a pure state, then $F(\ket{\psi} \bra{\psi}, \bm{\sigma}) = \bra{\psi} \bm{\sigma} \ket{\psi}$.

  We may also express the fidelity in terms of the $L^1$ norm,

  $$
  F(\bm{\rho}, \bm{\sigma}) = \left\| \bm{\sigma^\frac{1}{2}} \bm{\rho^\frac{1}{2}} \right\|^2_1,
  $$

  where $||\bm{A}||_1 = \text{tr} \sqrt{\bm{A}^\dagger \bm{A}}$.

+ It is useful to know how the fidelity of two density operators is related to the overlap of their purifications. A particular purification of $\bm{\rho}$ has the form

  $$
  \ket{\Psi_{\bm{\rho}}} = \sum_i \sqrt{p_i} \ket{i}_A \otimes \ket{i}_B,
  $$

  where $\{\ket{i}_A\}$ and $\{\ket{i}_B\}$ are orthonormal bases for systems A and B, respectively. According to the HJW theorem, a general purification has the form

  $$
  \ket{\Psi_{\bm{\rho}}(\bm{V})} = (\bm{I}_A \otimes \bm{V}_B) \ket{\Psi_{\bm{\rho}}},
  $$

  where $\bm{V}_B$ is an arbitrary unitary operator acting on system B. It can be expressed more generally as

  $$
  \ket{\Psi_{\bm{\rho}}(\bm{V})} = (\bm{\rho}^\frac{1}{2} \otimes \bm{V}_B) \ket{\tilde{\Psi}},
  $$

  where $\ket{\tilde{\Psi}} = \sum_i \ket{i}_A \otimes \ket{i}_B$ is the unconventionally normalized maximally entangled state.

  If $\bm{\rho}$ and $\bm{\sigma}$ are two density operators on $A$, the inner product of their purifications on $AB$ can be expressed as

  $$
  \langle \Psi_{\bm{\sigma}}(\bm{W}) | \Psi_{\bm{\rho}}(\bm{V}) \rangle = \langle \tilde{\Psi} | \bm{\sigma}^\frac{1}{2} \bm{\rho}^\frac{1}{2} \otimes \bm{W}^\dagger \bm{V} | \tilde{\Psi} \rangle.
  $$

  Noting that

  $$
  \bm{I} \otimes \bm{U} \ket{\tilde{\Psi}} = \sum_{ij} \ket{i}_A \otimes U_{ji} \ket{j}_B = \sum_{ij} U^T_{ij} \ket{i}_A \otimes \ket{j}_B = \bm{U^T} \otimes \bm{I} \ket{\tilde{\Psi}},
  $$

  we have,

  $$
  \langle \Psi_{\bm{\sigma}}(\bm{W}) | \Psi_{\bm{\rho}}(\bm{V}) \rangle = \langle \tilde{\Psi} | \bm{\sigma}^\frac{1}{2} \bm{\rho}^\frac{1}{2} \bm{U} \otimes \bm{I} | \tilde{\Psi} \rangle = \text{tr}(\bm{\sigma}^\frac{1}{2} \bm{\rho}^\frac{1}{2} \bm{U}),
  $$

  where $\bm{U} = (\bm{W}^\dagger \bm{V})^T$.

  Now we may use the polar decomposition

  $$
  \bm{A} = \bm{U'} \sqrt{\bm{A}^\dagger \bm{A}},
  $$

  where $\bm{U'}$ is a unitary operator, to rewrite the inner product as

  $$
  \langle \Psi_{\bm{\sigma}}(\bm{W}) | \Psi_{\bm{\rho}}(\bm{V}) \rangle = \text{tr}(\sqrt{\bm{\rho}^\frac{1}{2} \bm{\sigma} \bm{\rho}^\frac{1}{2}} \bm{U'} \bm{U}) = \sum_a \lambda_a \bra{a} \bm{U'} \bm{U} \ket{a},
  $$

  where $\lambda_a$ are the eigenvalues of $\sqrt{\bm{\rho}^\frac{1}{2} \bm{\sigma} \bm{\rho}^\frac{1}{2}}$ and $\{\ket{a}\}$ is the corresponding orthonormal basis. By choosing $\bm{U} = \bm{U'}^\dagger$, we can maximize the inner product. Thus we have:

  $$
  F(\bm{\rho}, \bm{\sigma}) = \max_{\ket{\Psi_{\bm{\rho}}}, \ket{\Psi_{\bm{\sigma}}}} |\langle \Psi_{\bm{\sigma}} | \Psi_{\bm{\rho}} \rangle|^2,
  $$

  The fidelity of two density operators is the maximal possible overlap of their purifications, a result called Uhlmann’s theorem. One corollary of Uhlmann’s theorem is the monotonicity of fidelity:

  $$
  F(\bm{\rho_{AB}}, \bm{\sigma_{AB}}) \leq F(\bm{\rho_{A}}, \bm{\sigma_{A}}),
  $$

  which says that tracing out a subsystem cannot decrease the fidelity of two density operators.

### 2.6.2 Relationships between distance measures

+ There are other possible ways besides fidelity for quantifying the difference between quantum states $\bm{\rho}$ and $\bm{\sigma}$, such as the distance between the states using the $L^1$ or $L^2$ norm,

  $$
  ||\bm{\rho} - \bm{\sigma}||_1 \text{ or } ||\bm{\rho} - \bm{\sigma}||_2,
  $$

  where the $L^2$ norm of an operator is defined by

  $$
  ||\bm{A}||_2 = \sqrt{\text{tr} \bm{A^\dagger} \bm{A}}.
  $$

  If $\{|\lambda_i|, i = 0, 1, 2, \ldots d-1\}$ denotes the eigenvalues of $\sqrt{\bm{A}^\dagger \bm{A}}$, then

  $$
  ||\bm{A}||_1 = \sum_{i=0}^{d-1} |\lambda_i|, ~~~ ||\bm{A}||_2 = \sqrt{\sum_{i=0}^{d-1} |\lambda_i|^2}.
  $$

  According to the Cauchy-Schwarz inequality, we have

  $$
  ||\bm{A}||_1 ≤ \sqrt{d} ||\bm{A}||_2.
  $$

  Because of the factor of $\sqrt{d}$ on the right hand side, for a high-dimensional system density operators which are close together in the $L^2$ norm might not be close in the $L^1$ norm.

+ We can derive a dimension-independent inequality relating the $L^1$ distance between $\bm{\rho}$ and $\bm{\sigma}$ and the $L^2$ distance

  $$
  \sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}} = \sum_i \lambda_i \ket{i} \bra{i},
  $$

  where $\lambda_i$ are the eigenvalues of the operator $\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}$ and $\{\ket{i}\}$ is the corresponding orthonormal basis. Then we note that the absolute value of this difference may be written as

  $$
  |\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}| = \sum_i |\lambda_i| \ket{i} \bra{i} = (\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}) \bm{U} = \bm{U} (\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}),
  $$

  where $\bm{U} = \sum_i \text{sign}(\lambda_i) \ket{i} \bra{i}$ is a unitary operator. Using

  $$
  \bm{\rho} - \bm{\sigma} = \frac{1}{2} (\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}})(\sqrt{\bm{\rho}} + \sqrt{\bm{\sigma}}) + \frac{1}{2} (\sqrt{\bm{\rho}} + \sqrt{\bm{\sigma}})(\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}),
  $$

  and the cyclicity of the trace, we find

  $$
  \begin{align*}
  \text{tr} [(\rho - \sigma) \bm{U}] &= \text{tr} [|\sqrt{\rho} - \sqrt{\sigma}|(\sqrt{\rho} + \sqrt{\sigma})] = \sum_i |\lambda_i| \bra{i} \sqrt{\rho} + \sqrt{\sigma} \ket{i} \\ &\geq \sum_i |\bra{i} \sqrt{\rho} - \sqrt{\sigma} \ket{i}| = \sum_i |\lambda_i|^2 = ||\sqrt{\rho} - \sqrt{\sigma}||^2_2.
  \end{align*}
  $$

  Finally, using

  $$
  ||\bm{\rho} - \bm{\sigma}||_1 = \text{tr} |\bm{\rho} - \bm{\sigma}| \geq \text{tr} [(\bm{\rho} - \bm{\sigma}) \bm{U}],
  $$

  we have

  $$
  ||\bm{\rho} - \bm{\sigma}||_1 \geq ||\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}||_2^2.
  $$

  This $L^2$ distance between square roots can be related to fidelity. First we note that

  $$
  ||\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}||_2^2 = \text{tr}[(\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}})^2] = \text{tr}(\bm{\rho} + \bm{\sigma} -2 \sqrt{\bm{\rho}} \sqrt{\bm{\sigma}}) = 2 - 2 \text{tr}(\sqrt{\bm{\rho}} \sqrt{\bm{\sigma}}),
  $$

  since $\text{tr} \bm{\rho} = \text{tr} \bm{\sigma} = 1$. From the polar decomposition $A = U \sqrt{A^\dagger A}$ (where $U$ is unitary), we see that $\text{tr} \sqrt{A^\dagger A} \geq |\text{tr} A|$, and therefore

  $$
  \sqrt{F(\bm{\rho}, \bm{\sigma})} = \text{tr} \sqrt{\bm{\rho^\frac{1}{2}} \bm{\sigma} \bm{\rho^\frac{1}{2}}} \geq |\text{tr}(\sqrt{\bm{\rho}} \sqrt{\bm{\sigma}})|;
  $$

  hence,

  $$
  \sqrt{F(\bm{\rho}, \bm{\sigma})} \geq 1 - \frac{1}{2} ||\sqrt{\bm{\rho}} - \sqrt{\bm{\sigma}}||_2^2 \geq 1 - \frac{1}{2} ||\bm{\rho} - \bm{\sigma}||_1
  $$

  The $L^1$ distance also provides an upper bound on fidelity:

  $$
  F(\bm{\rho}, \bm{\sigma}) \leq 1 - \frac{1}{4} ||\bm{\rho} - \bm{\sigma}||_1^2.
  $$

  This formula is relatively complicated and will not be proved here. By combining these two inequalities we have

  $$
  1 - \sqrt{F(\bm{\rho}, \bm{\sigma})} \leq \frac{1}{2} ||\bm{\rho} - \bm{\sigma}||_1 \leq \sqrt{1- F(\bm{\rho}, \bm{\sigma})}.
  $$

&nbsp;

&nbsp;

&nbsp;

# Chap 3 &nbsp;&nbsp;&nbsp; Measurement and Evolution [📖](https://www.preskill.caltech.edu/ph219/chap3_15.pdf)

## 3.1 Orthogonal measurement and Generalized measurement

+ 