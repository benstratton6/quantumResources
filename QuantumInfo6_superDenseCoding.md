---
title: Super-dense Coding
subject: Tutorial
subtitle: 
# short_title: How to MyST
authors:
  - name: Benjamin Stratton
    # affiliations:
    #   - Executable Books
    #   - Curvenote
    orcid: 0009-0001-2746-3668
    email: ben.stratton@bristol.ac.uk
license: 
keywords: Super-dense coding, classical information, classical capacity.  
abstract: Details of the task of super-dense coding where the consumption of one entangled state allows two classical bits to be communicated by sending one qubit.    
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Setup 

Let there be two spatially separated parties, Alice (A) and Bob (B), who share a $d=2$ dimension maximally entangled bipartite state,
\begin{equation}
\ket{\Phi^{+}_{00}}_{AB} = \frac{\ket{0}_{A}\ket{0}_{B}+\ket{1}_{A} \ket{1}_{B}}{\sqrt{2}}~\in~\mathcal{H}_{A}^{2} \otimes \mathcal{H}_{B}^{2}.
\end{equation}

Alice can perform any local operation on her qubit and she can send the qubit in her system to Bob. 

By applying a local unitary to her system before she sends it, Alice is aiming to send two classical bits to Bob. Hence, by sending only one qubit to Bob, Alice wants to communicate two classical bits to Bob. 

(super_dense_coding_protocol_target)=
## Super-dense Coding Protocol

Alice wants to send two classical bits to Bob. 

**Firstly**, Alice encodes the two bits she wants to send by applying the following unitaries to the state in her system:
\begin{align*}
00 &\rightarrow \mathbb{I}, \\
01 & \rightarrow \mathbb{Z}, \\
10 & \rightarrow \mathbb{X}, \\
11 & \rightarrow \mathbb{Y}. 
\end{align*}

The shared state between Alice and Bob will depend on the two bits Alice encodes. Specifically, the shared state will be one of the [Bell states](https://en.wikipedia.org/wiki/Bell_state), 
\begin{align*}
00 &\rightarrow \ket{\Phi_{00}^{+}} = \frac{\ket{0}_{A}\ket{0}_{B}+\ket{1}_{A} \ket{1}_{B}}{\sqrt{2}}, \\
01 & \rightarrow \ket{\Phi_{01}^{+}} = \frac{\ket{0}_{A}\ket{0}_{B}-\ket{1}_{A} \ket{1}_{B}}{\sqrt{2}}, \\
10 & \rightarrow \ket{\Phi_{10}^{+}} = \frac{\ket{0}_{A}\ket{1}_{B}+\ket{1}_{A} \ket{0}_{B}}{\sqrt{2}}, \\
11 & \rightarrow \ket{\Phi_{11}^{+}} = \frac{\ket{0}_{A}\ket{1}_{B}-\ket{1}_{A} \ket{0}_{B}}{\sqrt{2}}. 
\end{align*}

**Secondly**, Alice sends the state in her system to Bob. Bob now has both parts of the state.

**Lastly**, Bob measures the operator, $O$, which has the [Bell states](https://en.wikipedia.org/wiki/Bell_state) as its eigenvectors,
\begin{equation}
O = \lambda_{00} \ket{\Phi^{+}_{00}}\bra{\Phi^{+}_{00}} + \lambda_{01} \ket{\Phi^{+}_{01}}\bra{\Phi^{+}_{01}} + \lambda_{10} \ket{\Phi^{+}_{10}}\bra{\Phi^{+}_{10}} + \lambda_{11} \ket{\Phi^{+}_{11}}\bra{\Phi^{+}_{11}},
\end{equation}
where $\lambda_{00} \neq \lambda_{01} \neq \lambda_{10} \neq \lambda_{11}$. Bob decodes which two bits Alice sent based on the measurement outcome he gets,

\begin{align*}
\lambda_{00} &\rightarrow 00, \\
\lambda_{01} &\rightarrow 01,\\
\lambda_{10} &\rightarrow 10, \\
\lambda_{11} &\rightarrow 11. \\
\end{align*}

Therefore, by sending one qubit, that is part of a maximally entangled state, Alice is able to send Bob two bits. 

## Higher Dimensional Systems

The super-dense coding protocol can be generalised to allow Alice to communicate $n= \log_{2}(d^{2})$ bits to Bob by sending him half of a $d$ dimensional maximally entangled state, 
\begin{equation}
\ket{\Phi^{+}_{00}}_{AB} = \frac{1}{\sqrt{2}} \sum^{d-1}_{i=0} \ket{ii}~\in~\mathcal{H}_{A}^{d} \otimes \mathcal{H}_{B}^{d}.
\end{equation} 

**Firstly**, Alice encodes the $n$ bit string she wants to send to Bob by applying one of the so called [Heisenberg-Weyl operators](#Weyl_operators_target) to her half of the maximally entangled state. The $n$ bit-string Alice wants to encode can be captured by the pair of values $(a,b)$. Alice applies the unitary $W_{a,b}$ if she wants to communicate the bit-string associated to the pair of values $(a,b)$. 

The state shared between Alice and Bob will then be one element of a maximally entangled basis. See [generating a maximally entangled basis](#Generating_Maximally_Entangled_Basis_target) for more details on this. 

**Secondly**, Alice sends the state in her system to Bob. Bob now has both parts of the state.

**Lastly**, Bob measures the operator which has the maximally entangled basis as its eigenvectors (and is not degenerate). Bob will know which $n$ bit-string Alice wanted to communicate with certainty conditioned on the outcome of this measurement 

Therefore, by sending one $d$ dimensional state, that is part of a maximally entangled state, Alice is able to send Bob $n = \log_{2}(d^{2})$ bits.

## Further Details 

:::{dropdown} Super-dense Coding and Sub-Channel Discrimination


To perform super-dense coding, Alice and Bob must perform sub-channel discrimination. 

Alice plays the role of the refree, applying one of a set of pre-determined sub-channels to the reference state, $\ket{\Phi^{+}_{00}}_{AB}$. She then sending the reference state to Bob who aims to perform a measurement that allows him to identify which sub-channel Alice applied. Alice and Bob can choose to associate to each sub-channel a different bit-string. Hence, Alice has communicated some bit-string to Bob if he can correctly identify with sub-channel she applied. 

In order to perform conclusive state discrimination, the set of possible states Alice (the referee) sends to Bob must be orthogonal. If Alice sends Bob one unentangled qubit, there are only two orthogonal states Alice could send. This means that Bob can at most perform conclusive state discrimination between two different states, allowing only one bit to be sent with certainty. If Alice sends Bob a qubit that is part of a maximally entangled state, then there are four orthogonal states Alice could send. This allows Bob to perform conclusive state discrimination between four different states, allowing two bits to be sent.   

Using the mathematical machinery of state discrimination, one can therefore evaluate how successfully Alice and Bob can communicate classical information when using a partially entangled state -  a state that is not maximally entangled. Alice can choose optimal encodings that allow Bob the lowest probability of failure when performing state discrimination on those states after encoding. 

:::

:::{dropdown} Super-dense Coding and Teleportation 

In the task of [teleportation](#Teleportation_protocol_target), Alice and Bob send two classical bits and use one maximally entangled state to send a qubit from Alice to Bob. In terms of the tasks resource requirments, this can be written as 
\begin{equation}
qq + 2[c \rightarrow c] = [q \rightarrow q],
\end{equation}
where $qq$ is a maximally entangled state, $[c \rightarrow c]$ is the sending of a classical bits from Alice and Bob and $[q \rightarrow q]$ is the sending of a qubit from Alice to Bob ([noiseless teleportation](#noisy_teleportation_target) is considered here, hence the equality).

In the task of [super-dense coding](#super_dense_coding_protocol_target), Alice and Bob send one qubit and use one maximally entangled state to send two classical bits from Alice to Bob. Considering this again it terms of resource requirements gives 
\begin{equation}
qq + [q \rightarrow q] = 2[c \rightarrow c].
\end{equation}

:::
