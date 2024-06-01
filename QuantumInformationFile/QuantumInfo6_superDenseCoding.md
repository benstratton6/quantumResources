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
\ket{\Phi^{+}_{00}}_{AB} = \frac{\ket{0}_{A}\ket{0}_{B}+\ket{1}_{A} \ket{1}_{B}}{\sqrt{2}}~\in~\mathcal{H}_{A} \otimes \mathcal{H}_{B}.
\end{equation}

Alice can perform any local operation on her qubit and she can send the qubit in her system to Bob. 

By applying a local unitary to her system before she sends it, Alice is aiming to send two classical bits to Bob. Hence, by sending only one qubit to Bob, Alice wants to communicate two classical bits to Bob. 

## Super-dense Coding Protocol

Alice wants to send two classical bits to Bob. 

**Firstly**, Alice encodes the two bits she wants to send by applying the following unitary to her the state in her system:
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


## Further Details 

:::{dropdown} Links to State Discrimination
:open:

At the end of protocol, Bob performs state discrimination. 

Alice encodes the different combinations of two bits into orthogonal states. She therefore has a set of states, 

with each state  This allows Bob to perform a measurement where he is able

and Bob is able to perfectly Using the framework of state discrimination, one can model how many classical bits can be sent 

:::

