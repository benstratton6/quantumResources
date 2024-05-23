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

Contents: 
- Expectation Values Squared
- Moving Operators on Entangled States
- Alternative Bipartition of Entangled States
- Generating Maximally Entangled Basis


<!-- ```{card} 
:header: **Expectation Values Squared** 

Let $A$ be some operator and $\ket{\psi}$ be some state.

\begin{equation}
\bra{\psi} A \ket{\psi}^{2} = \bra{\psi}\bra{\psi} A \otimes A \ket{\psi}\ket{\psi}
\end{equation}
``` -->

<!-- ```{card} 
:header: **Moving Operators on Entangled States** 

Let $A$ be some operator and $\ket{\Phi^{+}}$ be a bipartite maximally entangled state.

\begin{equation}
(A \otimes \mathbb{I}) \ket{\Phi^{+}} = (\mathbb{I} \otimes A^{t}) \ket{\Phi^{+}},
\end{equation}
where $(\cdot)^{t}$ is the transpose operation. 

:::{dropdown} Proof
:closed:
Let $A$ be some operator and $\ket{\Phi^{+}} = \frac{1}{\sqrt{d}} \sum_{i} \ket{ii}$ be the bipartite maximally entangled state.

Consider the elements of the vector $(A \otimes \mathbb{I}) \big( \ket{\Phi^{+}} \big)$ ,
\begin{align*}
\bra{kl} (A \otimes \mathbb{I}) \big( \ket{\Phi^{+}} \big) &= \frac{1}{\sqrt{d}} \sum_{i} \bra{kl} (A \otimes \mathbb{I}) \ket{ii}, \\
&= \frac{1}{\sqrt{d}} \sum_{i} \bra{k} A \ket{i} \bra{l}\ket{i}, \\
&= \frac{1}{\sqrt{d}} \sum_{i} \bra{k} A \ket{i} \delta_{li}, \\
&= \frac{1}{\sqrt{d}} \bra{k} A \ket{l}.
\end{align*}

Consider the elements of the vector $(\mathbb{I} \otimes A^{t}) \big( \ket{\Phi^{+}} \big)$ ,

\begin{align*}
\bra{kl} (\mathbb{I} \otimes A^{t}) \big( \ket{\Phi^{+}} \big) &= \frac{1}{\sqrt{d}} \sum_{i} \bra{kl} (\mathbb{I} \otimes A^{t}) \ket{ii}, \\
&= \frac{1}{\sqrt{d}} \sum_{i}  \bra{k}\ket{i} \bra{l} A^{t} \ket{i}, \\
&= \frac{1}{\sqrt{d}} \sum_{i} \bra{l} A^{t} \ket{i} \delta_{ki},\\
&= \frac{1}{\sqrt{d}} \bra{l} A^{t} \ket{k},\\
&= \frac{1}{\sqrt{d}} \bra{k} A \ket{l}. 
\end{align*}

If the elements of these two vector are the same, they must be the same vector. This completes the proof. 

:::
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

```{card} 
:header: **Generating Maximally Entangled Basis**

Given a maximally entangled bipartite state, $\ket{\Phi^{+}_{00}}$, one can generate a complete maximally entangled basis using the Heisenberg-Weyl operators.

In a space of local dimenions $d$, the Heisenberg-Weyl operators are defined as 
\begin{equation}
W_{a,b} = U^{a}V^{b} = \sum_{k=0}^{d-1} \Omega^{bk} \ket{k+a}\bra{k},
\end{equation}
where $a,b~\in~\{0,1,\ldots,d-1 \}$ and
\begin{equation}
U = \sum_{k=0}^{d-1} \ket{k+1}\bra{k}, ~ ~ V = \sum^{d-1}_{k=0} \Omega^{k} \ket{k}\bra{k}, ~ ~ \Omega = e^{\frac{2 \pi i}{d}}.
\end{equation} 

$U$ and $V$ are  $X$ and $Z$ Pauli operators generalized to higher dimension. 

The set of states, 
\begin{equation}
\{ \ket{\Phi_{ab}^{+}} : a,b~\in~\{0,1,\ldots,d-1 \} \},
\end{equation}
where $\ket{\Phi_{ab}^{+}} = (\mathbb{I} \otimes W_{a,b}) \big( \ket{\Phi^{+}_{00}} \big)$ then forms a complete maximally entangled basis. 

:::{dropdown} Properties of Heisenberg-Weyl operators
:closed:
\begin{equation}
    \begin{split}
        & (W_{\alpha, \beta}) ^ {t} = \Omega^{-\alpha \beta}W_{-\alpha, \beta}, \\
        & (W_{\alpha, \beta}) ^ {\dagger} = \Omega^{\alpha \beta}W_{-\alpha, -\beta}, \\
        & W_{\alpha, \beta}W_{\gamma, \delta} = \Omega^{\beta\gamma}W_{\alpha + \gamma, \beta + \delta} = \Omega^{\beta\gamma - \alpha\delta}W_{\gamma, \delta}W_{\alpha, \beta}. \\ 
        & \textrm{tr}\big[ W_{a,b} \big] = \left
              \begin{array}{ll}
                n  & \mbox{if } (a,b) = (0,0) \\
                0 & \mbox{if } \textrm{otherwise}
              \end{array}
            \right.
    \end{split}
\end{equation}

For qubits, the Heisenberg-Weyl operators are 
\begin{equation}
W_{0,0} = \mathbb{I}, ~~ W_{0,1} = \sigma_{z}, ~~ W_{1,0} = \sigma_{x}, ~~ W_{1,1} = -i \sigma_{y}
\end{equation}
:::

``` -->