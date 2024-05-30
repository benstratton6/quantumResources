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
\ket{\Phi^{+}} = \frac{\ket{00}+\ket{11}}{\sqrt{2}}.
\end{equation}

It is assumed they have the ability to perform any operation on a quantum system in their respective labs and that they can send any amount of classical information to each other [💭](#classical_information_quantum_info_glossary). This is a set of operations know as *local operations and classical communication* ([LOCC](https://en.wikipedia.org/wiki/LOCC)) [💭](#LOCC_quantum_info_glossary).

Alice has a single copy of the qubit,
\begin{equation}
\ket{\psi} = \alpha \ket{0} + \beta \ket{1},
\end{equation}
in her laboratory that she wants to send it to Bob. Given Alice and Bob can only send classical information to each other, Alice cannot send the qubit to Bob directly. 

:::{dropdown} Alice has multiple copies of the qubit
:closed:

If Alice had many copies of $\ket{\psi}$ she could measure the operator 
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
to get the state $\ket{\psi}$. Note, this can be performed up to the precision with which Alice can encode $\alpha$ and $\beta$. 

As well as being much more resource intensive (many copies of $\ket{\psi}$ are needed), this method also mean both Alice and Bob to know what the qubit is.  

:::

## Teleportation Protocol


## Higher Dimensional Systems


## Links to the Resource Theory of Entanglement


See here for more on [Weyl operators](#Weyl_operators_target). 