---
title: Quantum Channels
subject: 
# subtitle: The space in which quantum states live
# short_title: How to MyST
authors:
  - name: Benjamin Stratton
    # affiliations:
    #   - Executable Books
    #   - Curvenote
    orcid: 0009-0001-2746-3668
    email: ben.stratton@bristol.ac.uk
# license: CC-BY-4.0
keywords: Dynamics, Channels, Evolution, Positive, Trace Preserving.   
abstract: The details of how the dynamics of quantum states are modelled.    
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Definition 

A quantum channel is a linear, completely positive, trace-preserving map (from the set of density operators to itself). 

A channel mapping from states in an input Hilbert space $\mathcal{H}_{in}$ to an output Hilbert space $\mathcal{H}_{out}$ is denoted as 
\begin{equation}
\mathcal{E}: \mathcal{H}_{in} \rightarrow \mathcal{H}_{out}
\end{equation}

A quantum channel is a more general notion of evolution then that captured via the Schrödinger equation and unitary dynamics as it models interactions with the environment. Unitary dynamics are subset of quantum channels. 

### Linear 

A map, $\mathcal{E}$, is linear if 
\begin{equation}
\mathcal{E}(\rho + \sigma) = \mathcal{E}(\rho) + \mathcal{E}(\sigma)
\end{equation}

### Positive 

A linear map, $\mathcal{E}$, is positive if it maps positive elements to positive elements,
\begin{equation}
\rho \geq 0 \implies \mathcal{E}(\rho) \geq 0.
\end{equation} 


### Completely Positive   

A linear map, $\mathcal{E}$, is completely positive if it remains a positive map when embedded into a high dimensional space,
\begin{equation}
\rho \geq 0 \implies (\mathcal{E} \otimes \mathcal{I}) (\rho) \geq 0,
\end{equation} 
where $\mathcal{I}$ is the identity channel on an arbitrarily large ancilla. 

This additional restriction is needed to ensure that acting that map on part of a larger, potentially entangled state, still outputs a physical quantum state. 

This ensure that all operators output from a channel remain positive semi-definite. 

### Trace-preserving

A map, $\mathcal{E}$, is trace preserving if 
\begin{equation}
\textrm{tr} \big[ \mathcal{E}(\rho) \big] = 1,
\end{equation}
for all $\rho \in \mathcal{H}_{in}$, where $\rho$ is a valid density operator, $ \textrm{tr} \big[ \rho \big] = 1, \rho \geq 0$. 

This ensure that all operators output from a channel still have trace one.

## Channel Descriptions

There are multiple different ways to represent a quantum channel. Each different channel description can be used whenever useful. 

::::{tab-set}
:::{tab-item} Stinespring Dilation
:sync: tab1

Let $\mathcal{E}: \mathcal{H}_{S} \rightarrow \mathcal{H}_{S'}$ be a quantum channel and $\rho~\in~\mathcal{H}_{S}$. 

There exists a state, $\tau_{E}~\in~\mathcal{H}_{E}$, and isometry, $U_{SE}$, such that 
\begin{equation}
\mathcal{E}(\rho) = \textrm{tr}_{E} \big[ U_{SE}(\rho_{S} \otimes \tau_{E}) U_{SE}^{\dagger} \big],
\end{equation}
where the subscript $S$ and $E$ mean system and environment respectively.

The Stinespring dilation says that all channels can be consider unitary with respect to a higher dimensional space. That is, all channels are the interaction of $\rho$ and some environment state, $\tau$ under a global unitary. 

**Properties**

- $\textrm{dim} ~ \tau_{E} \leq d^{2}$ where $\textrm{dim} ~ \rho = d$
- Tracing out the system instead of the enviroment gives the complementary, $\mathcal{E}^{c}$, which can be thought as the channel from the perspective of the environment,
\begin{equation}
\mathcal{E}^{c}(\rho) = \textrm{tr}_{S} \big[ U_{SE}(\rho_{S} \otimes \tau_{E}) U_{SE}^{\dagger} \big].
\end{equation}

:::
:::{tab-item} Kraus Decomposition 
:sync: tab2

Let $\mathcal{E}: \mathcal{H}_{S} \rightarrow \mathcal{H}_{S'}$ be a quantum channel and $\rho~\in~\mathcal{H}_{S}$

There exists a set of $M$ operators $\{ K_{i} \}_{i=1}^{M}$ such that
\begin{equation}
\mathcal{E}(\rho) = \sum_{i=1}^{M} K_{i} \rho K_{i}^{\dagger},
\end{equation}
where 
\begin{equation}
\sum_{i=1}^{M} K_{i}^{\dagger}K_{i} = \mathbb{I}.
\end{equation}

This condition ensures that the quantum channel is trace preserving. 

The Kraus decomposition allows one to apply channels without having to consider the environment. 

**Properties** 
- The Kraus decomposition is not unique. Although, if there are two sets of operators that both describe the same channel, those sets of operators are unitarily equivalent. 
- $M \leq \dim \mathcal{H}_S \times \dim \mathcal{H}_{S'}$, meaning the number of operators needed for the Kraus decomposition is upper-bounded by the product of the dimensions of the input and output spaces. 

:::
:::{tab-item} Choi-Jamiolkowski isomorphism
:sync: tab3

Let $\mathcal{E}: \mathcal{H}_{S} \rightarrow \mathcal{H}_{S'}$ be a quantum channel,$~\rho~\in~\mathcal{H}_{S}$ be a state, and $\ket{\Phi}_{SS}~\in~\mathcal{H}_{S} \otimes \mathcal{H}_{S}$ a full [Schmit rank state](https://en.wikipedia.org/wiki/Schmidt_decomposition) with $\textrm{dim} ~ \mathcal{H}_{S} \approx \textrm{dim} ~ \mathcal{H}_{S'}$. 

 The Choi-Jamiolkowski isomorphism ([](https://doi.org/10.1016/0034-4877(72)90011-0), [](https://doi.org/10.1016/0024-3795(75)90075-0)) is a linear mapping between quantum channels and bipartite quantum states defined by
\begin{equation}
    \mathcal{J}^{\mathcal{E}}_{\rm S'S} = (\mathcal{N}_{\rm S} \otimes \mathcal{I}_{\rm S}) \big( \ket{\Phi}\bra{\Phi}_{\rm SS} \big)~\in~\mathcal{H}_{S'} \otimes \mathcal{H}_{S}, 
\end{equation}
where $\mathcal{I}_{\rm S}$ is an identity channel acting on $\mathcal{H}_{S}$.

Typically, the full Schmit rank state state is taken to be a maximally entangled state in a fixed orthonormal basis, 
\begin{equation}
\ket{\Phi}_{AB} = \frac{1}{\sqrt{d}} \sum_{i=0}^{d-1} \ket{i}_{A} \ket{i}_{B}.
\end{equation}

From the Choi-state, the action of $\mathcal{E}$ on a state $ \rho $ can be recovered as 
\begin{equation}
\mathcal{E}(\rho) = d ~ \textrm{tr}_{\rm S}\left[ \left(\mathbb{I}_{\rm S} \otimes \rho^{t}\right) \mathcal{J}^{\mathcal{N}}_{\rm S'S} \right],
\end{equation}
where $(\cdot)^{t}$ is the transpose operation in the given fixed basis of the full Schmit rank state and $ \mathbb{I}_{\rm S} $ is the identity operator on $\mathcal{H}_{S}$. 

:::
::::