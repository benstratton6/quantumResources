---
title: Useful Tricks
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
keywords:  
abstract: Some useful tricks that could prove useful in proofs
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

```{card} 
:header: **Expectation Values Squared** 

Let $A$ be some operator and $\ket{\psi}$ be some state

\begin{equation}
\bra{\psi} A \ket{\psi}^{2} = \bra{\psi}\bra{\psi} A \otimes A \ket{\psi}\ket{\psi}
\end{equation}
```

```{card} 
:header: **Alternative Bipartition of Entangled States** 

Let $\ket{\Phi^{+}}_{AB}~\in~\mathcal{H}_{A} \otimes \mathcal{H}_{B}$ be the maximally entangled stated between a space $A$ and $B$. Let $\ket{\Phi^{+}}_{CD}~\in~\mathcal{H}_{C} \otimes \mathcal{H}_{D}$ be the maximally entangled stated between a space $C$ and $D$

\begin{equation}
\ket{\Phi^{+}}_{AB} \otimes \ket{\Phi^{+}}_{CD} = \ket{\Phi^{+}}_{(AC),(BD)}
\end{equation}

where $\ket{\Phi^{+}}_{(AC),(BD)}$ is the maximally entangled state between $(AC)$ and $(BD)$. 

This can be generalised to more tensor products of the maximally entangled state, e.g 
\begin{equation}
\ket{\Phi^{+}}_{AB} \otimes \ket{\Phi^{+}}_{CD} \otimes \ket{\Phi^{+}}_{EF} = \ket{\Phi^{+}}_{(ACE),(BDF)}
\end{equation}

:::{dropdown} Proof
:closed:
\begin{align*}
\ket{\Phi^{+}}_{AB} &= \frac{1}{\sqrt{2}} ( \ket{00}_{AB} + \ket{11}_{AB}) \\
\ket{\Phi^{+}}_{CD} &= \frac{1}{\sqrt{2}} ( \ket{00}_{CD} + \ket{11}_{CD}) \\
\end{align*}
\begin{align*}
&\ket{\Phi^{+}}_{AB} \otimes \ket{\Phi^{+}}_{CD} \\
&= \frac{1}{\sqrt{2}} ( \ket{00}_{AB} + \ket{11}_{AB}) \otimes \frac{1}{\sqrt{2}} ( \ket{00}_{CD} + \ket{11}_{CD}) \\
&= \frac{1}{2} (\ket{0000}_{ABCD} + \ket{0011}_{ABCD} + \ket{1100}_{ABCD} + \ket{1111}_{ABCD}) 
\end{align*}
The labels on the $B$ and $C$ particles can then be swapped. 
\begin{align*}
&= \frac{1}{2} (\ket{0000}_{ACBD} + \ket{0101}_{ACBD} + \ket{1010}_{ACBD} + \ket{1111}_{ACBD}) \\ 
\end{align*}
Rewriting the binary with 
\begin{align*}
00 &\rightarrow 0, \\
01 &\rightarrow 1, \\
10 &\rightarrow 2, \\
11 &\rightarrow 3, \\
\end{align*} 
and grouping the spaces together gives 
\begin{align*}
&= \frac{1}{2} (\ket{00}_{(AC)(BD)} + \ket{11}_{(AC)(BD)} + \ket{22}_{(AC)(BD)} + \ket{33}_{(AC)(BD)}) \\ 
&= \ket{\Phi^{+}}_{(AB)(CD)},
\end{align*}
completing the proof. 
:::
```