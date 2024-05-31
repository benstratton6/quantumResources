---
title: Teleportation
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
keywords: Teleportation, Entanglement, LOCC.  
abstract: Details of the task of quantum state Teleportation.   
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

It is assumed they have the ability to perform any operation on a quantum system in their respective labs and that they can send any amount of classical information to each other [💭](#classical_information_quantum_info_glossary). These operations are known the set of *local operations and classical communication* ([LOCC](https://en.wikipedia.org/wiki/LOCC)) [💭](#LOCC_quantum_info_glossary).

Alice has a single copy of the qubit,
\begin{equation}
\ket{\psi}_{A_1} = \alpha \ket{0}_{A_1} + \beta \ket{1}_{A_1}~\in~\mathcal{H}_{A_{1}},
\end{equation}
in her laboratory that she wants to send to Bob. The subscript $A_1$ shows that the state is in Alice's lab. Given Alice and Bob can only send classical information to each other, Alice cannot send the qubit to Bob directly. 


## Teleportation Protocol

Alice can instead send the qubit $\ket{\psi}_{A_1}$ to Bob via the [quantum teleportation protocol](10.1103/PhysRevLett.70.1895).  

The quantum teleportation protocol states that it is possible for Alice to exactly send the state $\ket{\psi}_{A_1}$ to Bob using: a maximally entangled state, a measurement in a maximally entangled basis, two classical bits and one local unitary.  

*The Protocol*: 

The initial state shared between Alice and Bob is
\begin{align*}
\ket{\Psi}_{A_{1}AB} &= \ket{\psi}_{A_1} \otimes \ket{\Phi^{+}_{00}}_{AB}~\in~\mathcal{H}_{A_1} \otimes \mathcal{H}_{A} \otimes \mathcal{H}_{B}, \\
&= \big[ \alpha \ket{0}_{A_1} + \beta \ket{1}_{A_1} \big] \otimes \frac{1}{\sqrt{2}}\big[ \ket{0}_{A}\ket{0}_{B_1}+\ket{1}_{A} \ket{1}_{B} \big].
\end{align*} 

This state, $\ket{\Psi}_{A_{1}AB}$, can then be expanded and rewritten as 
\begin{align*}
\ket{\Psi}_{A_{1}AB} = \frac{1}{2 \sqrt{2}} \big[ \ket{0}_{A_1}\ket{0}_{A} + \ket{1}_{A_1}\ket{1}_{A} \big] \big[ \alpha \ket{0}_{B} + \beta \ket{1}_B \big] \\
+  \frac{1}{2 \sqrt{2}} \big[ \ket{0}_{A_1}\ket{0}_{A} - \ket{1}_{A_1}\ket{1}_{A} \big] \big[ \alpha \ket{0}_{B} - \beta \ket{1}_B \big] \\
+ \frac{1}{2 \sqrt{2}} \big[ \ket{0}_{A_1}\ket{1}_{A} + \ket{1}_{A_1}\ket{0}_{A} \big] \big[ \beta \ket{0}_{B} + \alpha \ket{1}_B \big] \\
+ \frac{1}{2 \sqrt{2}} \big[ \ket{0}_{A_1}\ket{1}_{A} - \ket{1}_{A_1}\ket{0}_{A} \big] \big[ - \beta \ket{0}_{B} + \alpha \ket{1}_B \big] .
\end{align*}

**Firstly**, Alice measures the operator, $O$, which has the [Bell states](https://en.wikipedia.org/wiki/Bell_state) as its eigenvectors,
\begin{equation}
O = \lambda_{00} \ket{\Phi^{+}_{00}}\bra{\Phi^{+}_{00}} + \lambda_{01} \ket{\Phi^{+}_{01}}\bra{\Phi^{+}_{01}} + \lambda_{10} \ket{\Phi^{+}_{10}}\bra{\Phi^{+}_{10}} + \lambda_{11} \ket{\Phi^{+}_{11}}\bra{\Phi^{+}_{11}},
\end{equation}
where $\lambda_{00} \neq \lambda_{01} \neq \lambda_{10} \neq \lambda_{11}$, and 
\begin{align*}

\ket{\Phi_{00}^{+}} &= \frac{\ket{0}_{A}\ket{0}_{B}+\ket{1}_{A} \ket{1}_{B}}{\sqrt{2}}, \\
\ket{\Phi_{01}^{+}} &= \frac{\ket{0}_{A}\ket{0}_{B}-\ket{1}_{A} \ket{1}_{B}}{\sqrt{2}}, \\
\ket{\Phi_{10}^{+}} &= \frac{\ket{0}_{A}\ket{1}_{B}+\ket{1}_{A} \ket{0}_{B}}{\sqrt{2}}, \\
\ket{\Phi_{11}^{+}} &= \frac{\ket{0}_{A}\ket{1}_{B}-\ket{1}_{A} \ket{0}_{B}}{\sqrt{2}}, \\

\end{align*}

on the spaces $\mathcal{H}_{A_{1}} \otimes \mathcal{H}_{A}$. Alice gets one the eigenvalues of $O$ as her measurement outcome.

After Alice measures $O$, the state of Bob's system is dependent on Alice's measurement outcome, 

\begin{align*}

\lambda_{00} &\rightarrow \alpha \ket{0} + \beta \ket{1}~\in ~ \mathcal{H}_{B}, \\
\lambda_{01} &\rightarrow \alpha \ket{0} - \beta \ket{1}~\in ~ \mathcal{H}_{B}, \\
\lambda_{10} &\rightarrow \beta \ket{0} + \alpha \ket{1}~\in ~ \mathcal{H}_{B}, \\
\lambda_{11} &\rightarrow - \beta \ket{0} + \alpha \ket{1}~\in ~ \mathcal{H}_{B}. \\

\end{align*}

Therefore, based on her measurement outcome Alice knows which state Bob has in his system. Bob, however, does not know. 

**Secondly**, Alice communicates her measurement outcome to Bob, therefore informing him of the state of his system. Given there were four possible outcomes, $ \{ \lambda_{00}, \lambda_{01}, \lambda_{10}, \lambda_{11} \}$, she needs to send Bob two bits ($2^2 = 4$):
\begin{align*}
\lambda_{00} &\rightarrow \textrm{Alice sends}~ 00 \\
\lambda_{01} &\rightarrow \textrm{Alice sends}~ 01 \\
\lambda_{10} &\rightarrow \textrm{Alice sends}~ 10 \\
\lambda_{11} &\rightarrow \textrm{Alice sends}~ 11 \\
\end{align*}

After receiving the two bits from Alice, Bob knows which of four states he has (but not $ \alpha $ and $ \beta $ explicitly.) 

**Lastly**, and conditioned on the bits he receives from Alice, Bob applies one of four unitaries:
 
\begin{align*}
00 &\rightarrow \textrm{Bob applies}~ \mathbb{I}, \\
01 &\rightarrow \textrm{Bob applies}~ Z, \\
10 &\rightarrow \textrm{Bob applies}~ X, \\
11 &\rightarrow \textrm{Bob applies}~ Y. \\

\end{align*}

After this, Bob is left with the state $\ket{\psi}_{A_{1}}$ in his space. 

Hence, using one maximally entangled state, one measurement in the Bell basis, two classical bits and one local unitary the state $\ket{\psi}_{A_1}$ has "sent" from Alice to Bob. However, the physical state has *not* been sent, the information that defines the state has been. 


## Higher Dimensional Systems


## Teleportation in the Resource Theory of Entanglement  

In the teleportation protocol, after Alice measures $O$, Alice and Bob no longer share a maximally entangled state. The maximally entangled state has been "consumed" in order to implement the teleportation protocol. Given one cannot perform teleportation without an entangled state and it is consumed in the process it is considered a *resource* for the task. 

The teleportation protocol is an example of [simulating a channel](#simulation_of_channels_target) in a resource theory. Specifically, it allows the simulation of a noiseless quantum channel in the resource theory of entanglement. 

:::{dropdown} Details
:open:

The allowed operations of the resource theory of entanglement are LOCC, and the free states are the set of all product states. Hence, there is no channel in the set of allowed operations to noiselessly send a qubit between two spatially separated parties. 

However, when the two spatially separated parties shared an entangled state - a maximally resourceful state - there exists an allowed operation, an LOCC channel, that is able to simulate a noiseless channel that sends a quantum state from one party to another. Formally, 
\begin{equation}
\mathcal{T}(\rho \otimes \ket{\Phi^{+}}\bra{\Phi^{+}}_{AB}) \xrightarrow{simulates} \mathcal{N}_{A \rightarrow B}(\rho),
\end{equation}
where $\mathcal{T}~\in~\textrm{LOCC}$ is the quantum channel for the teleportation protocol and $\mathcal{N}~\notin~\textrm{LOCC}$ is the quantum channel that noiselessly sends the quantum state $ \rho $ from party $A$ to $B$. 

If the two spatially separated parties did not share an entangled state they would not be able to simulate the channel $\mathcal{T}$. However, if the had a partially entangled state - a state that is entangled but not maximally entangled - they can perform lower quality teleportation, as quantifed by the fidelity of teleportation. 


:::



## Further Details 

:::{dropdown} What if Alice has multiple copies of the qubit?
:closed:

If Alice had many copies of $\ket{\psi}_{A}$ she could measure the operator 
\begin{equation}
Z= \ket{0} \bra{0} - \ket{1} \bra{1},
\end{equation} 
and record the measurement outcomes. Over many measurements she will discover what $ \alpha $ and $ \beta $ are. Alice can then encode these values in classical information and send them to Bob along with a specification of the basis she measured in. 

Bob can then prepare the state $\ket{0}$ and apply the unitary 
\begin{equation}
U =\begin{pmatrix}
\alpha & - \beta^{*} \\
\beta & \alpha^{*} \\
\end{pmatrix},
\end{equation}
to get the state $\ket{\psi}_{A}$. Note, this can be performed up to the precision with which Alice can encode $\alpha$ and $\beta$. 

As well as being much more resource intensive (many copies of $\ket{\psi}_{A}$ are needed), this method also mean both Alice and Bob to know what the qubit is.  

:::

See here for more on [Weyl operators](#Weyl_operators_target). 