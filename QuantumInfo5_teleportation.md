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
abstract: Details of the task of quantum state Teleportation, in both the qubit and higher dimensional case. The fidelity of teleportation and teleportation from the perspective of the resource theory of entanglement is also discussed.    
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

It is assumed they have the ability to perform any operation on a quantum system in their respective labs and that they can send any amount of classical information to each other [💭](#classical_information_quantum_info_glossary). 

These operations are known as the set of *local operations and classical communication* ([$LOCC(A:B)$](https://en.wikipedia.org/wiki/LOCC)) [💭](#LOCC_quantum_info_glossary). They are a physically motivated set of operations as local manipulation of quantum states and classical communication between spatially separated parties are much easier to perform then the transportation of quantum states between spatially separated parties.  

Alice has a single copy of the qubit,
\begin{equation}
\ket{\psi}_{A_1} = \alpha \ket{0}_{A_1} + \beta \ket{1}_{A_1}~\in~\mathcal{H}_{A_{1}},
\end{equation}
in her laboratory that she wants to send to Bob. The subscript $A_1$ shows that the state is in Alice's lab. Given Alice and Bob can only send classical information to each other, Alice cannot send the qubit to Bob directly. 

(Teleportation_protocol_target)=
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

After Alice measures $O$, the state of Bob's system is dependent on Alice's measurement outcome: 

\begin{align*}

\lambda_{00} &\rightarrow \alpha \ket{0} + \beta \ket{1}~\in ~ \mathcal{H}_{B}, \\
\lambda_{01} &\rightarrow \alpha \ket{0} - \beta \ket{1}~\in ~ \mathcal{H}_{B}, \\
\lambda_{10} &\rightarrow \beta \ket{0} + \alpha \ket{1}~\in ~ \mathcal{H}_{B}, \\
\lambda_{11} &\rightarrow - \beta \ket{0} + \alpha \ket{1}~\in ~ \mathcal{H}_{B}. \\

\end{align*}

Therefore, based on her measurement outcome Alice knows which state Bob has in his system. Bob, however, does not know which of the above states he has in his system.

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

Hence, using one maximally entangled state, one measurement in the Bell basis, two classical bits and one local unitary, the state $\ket{\psi}_{A_1}$ has been "sent" from Alice to Bob. However, the physical state has *not* been sent, the information that defines the state has been. 

:::{dropdown} Diagram

```{figure} quantumTeleportationDiagram.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: quantumTeleportationDiagram

A graphical depiction of the quantum teleportation protocol.  
```
:::



## Fidelity of Teleportation 

One does not need a maximally entangled state to perform teleportation. However, using a partially entangled state - a state that is entangled but not maximally entangled - will reduce the quality of the teleportation, as measured by the fidelity of teleportation. This is a measure of how similar the final quantum state in Bob's space is to the initial state Alice is trying to teleport.  

:::{dropdown} Details

[The average fidelity of teleportation](https://link.aps.org/doi/10.1103/PhysRevLett.72.797) is given by 
\begin{align*}

F(\rho_{AB}) &= \max_{\mathcal{T}} \int \bra{\theta} \textrm{tr}_{A_{1}A}\mathcal{T}(\theta \otimes \rho_{AB}) \ket{\theta} d \theta, \\
& \textrm{s.t}~\mathcal{T}~\in~LOCC(A_{1}A:B),
\end{align*}
where $\rho_{AB}$ is a shared state between Alice and Bob, $ \theta $ is the state being teleported, where $\textrm{dim} \theta = d_{\theta}$, and $\mathcal{T}$ is the teleportation channel (this packages up the measurement of $O$, the classical communication and the local rotation). The fidelity is a measure of how well a state $ \rho_{AB} $ performs on average at teleporting all possible states in the space from Alice to Bob.

**Properties**
- $0 \leq F(\rho_{AB}) \leq 1$
- $F(\rho_{AB}) = 1$ iif $\rho_{AB}$ is the maximally entangled state. 
- If $\rho_{AB}$ is a separable state, then there exists a classical strategy such that $F(\rho_{AB}^{\textrm{sep}}) = 2/(d_{\theta}+1)$.
- [The fidelity of teleportation has been related to the entanglement fraction](https://link.aps.org/doi/10.1103/PhysRevA.60.1888) as
\begin{align*}

F(\rho_{AB}) &= \frac{f(\rho_{AB})d_{\theta}+1}{d_{\theta}+1},

\end{align*}
where 
\begin{align*}
f(\rho_{AB}) &\coloneqq \max_{\mathcal{E}} \bra{\Phi^{+}_{00}} \mathcal{E}(\rho_{AB}) \ket{\Phi^{+}_{00}} \\
& \mathcal{E} ~\in~LOCC(A:B).
\end{align*}
The entanglement fraction maximises the overlap between the state $\rho_{AB}$ and the maximally entangled state over all $LOCC(A:B)$ protocols. 

:::


## Higher Dimensional Systems

The teleportation protocol can be generalised to send higher dimensional states between two spatially separated parties. A state $\rho_{A_1}$, where $\textrm{dim} \rho_{A_1} = d_{A_1}$, can be teleported between Alice (A) and Bob (B) using a bipartie maximally entangled state of local dimension $d_{A_1}$,
\begin{equation}
\ket{\Phi^{+}_{00}}_{AB} = \frac{1}{\sqrt{2}} \sum^{d_{A_1}-1}_{i=0} \ket{ii}~\in~\mathcal{H}_{A}^{d_{A_1}}\otimes \mathcal{H}_{B}^{d_{A_1}}.
\end{equation}

**Firstly**, Alice measures the operator with a basis of maximally entangled states,
\begin{equation}
\{ (\mathbb{I} \otimes W_{a,b}) \big( \ket{\Phi^{+}_{00}}_{AB} \big) : (a,b)~\in~\{0, \ldots, d_{A_1}-1\} \},
\end{equation}
where $W_{a,b}$ are the so called [Heisenberg-Weyl operators](#Weyl_operators_target). See [generating a maximally entangled basis](#Generating_Maximally_Entangled_Basis_target) for more details on this.  

**Secondly**, Alice needs to send the results of her measurement outcome, which can be capture by pair of values $(a,b)$, to Bob. There are $d^{2}$ different pairs of values $(a,b)$, meaning Alice needs to send $n= \log_{2}(d^{2})$ bits to Bob. 

**Lastly**, if Bob receives the bits from Alice associated to a pair of values $(a',b')$, Bob applied $W_{a',b'}$ to his local system. Bob then has the $d_{A_1}$ dimensional state in his system.  
 

## Teleportation in the Resource Theory of Entanglement  

In the teleportation protocol, after Alice measures $O$, Alice and Bob no longer share a maximally entangled state; the maximally entangled state has been "consumed" in order to implement the teleportation protocol. Given one cannot perform teleportation without an entangled state and it is consumed in the process it is considered a [*resource*](#resource_theroies_introduction_page_target) for the task. 

The teleportation protocol is an example of [simulating a channel](#simulation_of_channels_target) in a resource theory. Specifically, the teleportation channel allows the simulation of a noiseless quantum channel in the resource theory of entanglement. 

:::{dropdown} Details


The allowed operations of the resource theory of entanglement are $LOCC(A:B)$ - local operations and classical communication between two spatially separated parties Alice ($A$) and Bob ($B$). The free states are the set of all product states, as any product state between Alice and Bob can be generated via $LOCC(A:B)$ and, given any product state between $A$ and $B$, no entanglement can be generated via $LOCC(A:B)$. 

There is no channel in the set of allowed operations to send a quantum state from Alice to Bob. However, when the two parties share an entangled state - a maximally resourceful state - there exists an allowed operation, that is an $ LOCC(A:B) $ channel, that is able to simulate a *noiseless* quantum channel that sends a quantum state from Alice to Bob. Formally, 
\begin{equation}
\textrm{tr}_{A_{1}A}\mathcal{T}(\rho_{A_1} \otimes \ket{\Phi^{+}}\bra{\Phi^{+}}_{AB}) \xrightarrow{simulates} \mathcal{N}_{A \rightarrow B}(\rho_{A_1}),
\end{equation}
where $\mathcal{T}~\in~LOCC(A_{1}A:B)$ is the quantum channel for the teleportation protocol and $\mathcal{N}~\notin~\textrm{LOCC}(A:B)$ is the quantum channel that noiselessly sends the quantum state $ \rho_{A_1} $ from Alice to Bob. 

(noisy_teleportation_target)=
As measured by the fidelity of teleportation, Alice and Bob can perform lower quality teleportation if $\rho_{AB}$ is entangled but not maximally entangled. In this case, the channel that is simulated is not noiseless, but instead noisy. Bob's final state will therefore not be exactly the state Alice tried to send. This furthers the notion of entanglement being a resource for this task; the amount of entanglement Alice and Bob shared dictates how noiselessly a quantum state can be sent from Alice to Bob. This can be succinctly formalised through the following equation
\begin{equation}
qq + 2[c \rightarrow c] \geq [q \rightarrow q],
\end{equation}
meaning that one entangled state, $qq$, and 2 classical bits, $2[c \rightarrow c]$ simulate a noiseless quantum channels sending a quantum state, $[q \rightarrow q]$. The inequality represents the fact that the noiseless channel is only achievable if $qq$ is the maximally entangled state. 


<!-- If the two spatially separated parties did not share an entangled state they would not be able to simulate the channel $\mathcal{T}$. However, if the had a partially entangled state - a state that is entangled but not maximally entangled - they can perform lower quality teleportation, as quantifed by the fidelity of teleportation.  -->


:::



<!-- ## Further Details 

:::{dropdown} What if Alice has multiple copies of the qubit she wants to send to Bob?


If Alice had many copies of $\ket{\psi}_{A_1}$ she could measure the operator 
\begin{equation}
Z= \ket{0} \bra{0} - \ket{1} \bra{1},
\end{equation} 
and record the measurement outcomes. Over many measurements she will discover what $ \abs{\alpha}^{2} $ and $ \abs{ \beta }^{2} $ are as the probabilities of each outcome occurring. Alice can then encode these values in classical information and send them to Bob along with a specification of the basis she measured in. 

Bob can then prepare the state $\ket{0}$ and apply the unitary 
\begin{equation}
U =\begin{pmatrix}
\alpha & - \beta^{*} \\
\beta & \alpha^{*} \\
\end{pmatrix},
\end{equation}
to get the state $\ket{\psi}_{A_1}$. Note, this can be performed up to the precision with which Alice can encode $\alpha$ and $\beta$. 

As well as being much more resource intensive (many copies of $\ket{\psi}_{A_1}$ are needed), this method also mean both Alice and Bob to know what the qubit is.  

::: -->

