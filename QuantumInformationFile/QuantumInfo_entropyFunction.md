---
title: Quantum Entropy Functions 
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
keywords: Entropy, Relative Entropy. 
abstract: Some Quantum entropy functions and their properties are given. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Von Neumann Entropy 

Let $\rho$ be a quantum state. The Von Neumann entropy of of $\rho$ is given by 
(Von_Neumann_Entropy_Equation_target)=
\begin{equation}
S(\rho) = -\textrm{tr}(\rho \log (\rho))
\end{equation}

It can be thought of as a measure of how far from a pure state a given state $\rho$ is.

:::{dropdown} Properties
:close:
1. $S(\rho) \geq 0$ where $S(\rho)=0$ iif $\rho$ is a pure state.
2. $ \max_{\rho} S(\rho)= \log{d}$ where $d$ is the dimension of the space. This occurs when $\rho$ is maximally mixed. 
3. $S(U \rho U^{\dagger}) = S(\rho)$ where $UU^{\dagger} = U^{\dagger}U = \mathbb{I}$. 
4. If $\sum_{i} p_i = 1$ then 
\begin{equation} 
S \bigg( \sum_{i} p_{i} \rho_i \bigg) \geq \sum_{i} p_{i} S(\rho_{i}).
\end{equation} 
5. $S(\rho \otimes \sigma) = S(\rho) \otimes S(\sigma)$.
6. $S(\rho_{AB}) \leq S(\rho_{A}) + S(\rho_{B})$, where $\rho_{A} = \textrm{tr}_{B}(\rho_{AB})$, etc.
7. $S(\rho_{AB}) \geq \vert S(\rho_{A}) - S(\rho_{B}) \vert$.
:::

## Quantum Relative Entropy 

Let $\rho, \sigma$ be quantum states. The quantum relative entropy is given by 
\begin{equation}
S( \rho \vert \vert \sigma) = \textrm{tr} \big( \rho \log(\rho) - \rho \log(\sigma)).
\end{equation}
if $\textrm{supp}(\rho) \subseteq \textrm{supp}(\sigma)$, it is defined as $+ \infty $ otherwise. 

It can be thought of as a measure of how similar two states $\rho$ and $\sigma$ are.

:::{dropdown} Properties
:close:
1. $S( \rho \vert \vert \sigma) \geq 0$
2. $S( \rho \vert \vert \sigma) \neq S( \sigma \vert \vert \rho)$
3. If $\mathcal{E}$ is a quantum channel then 
\begin{equation}
S( \rho \vert \vert \sigma) \geq S( \mathcal{E}(\rho) \vert \vert \mathcal{E}(\sigma)).
\end{equation}
  - This is the [data processing inequality.](https://en.wikipedia.org/wiki/Data_processing_inequality)
4. $S( \rho \vert \vert \mathbb{I}/d) = \log(d) - S(\rho)$
5. If $\sum_{i} p_i = 1$ then 
\begin{equation}
S \bigg( \sum_{i} p_i \rho_i \vert \vert \sum_i p_i \sigma_i \bigg) \leq \sum_i p_i S(\rho_i \vert \vert \sigma_i) 
\end{equation}
:::

## Quantum $\alpha$-Rényi Entropies 

Let $\rho$ be a quantum state, the $\alpha$-Rényi entropy of $\rho$ is given by
\begin{equation}
S_{\alpha} = \frac{1}{1-\alpha} \log(\textrm{tr}(\rho^{\alpha})), ~ \alpha \in (0,1) \cap (1, \infty). 
\end{equation}
These are a set of functions that generalise entropy functions (such as the [Von Neumann Entropy](#Von_Neumann_Entropy_Equation_target)) by satisfying many of the same properties for all $\alpha$.  

In the limit of $\alpha \rightarrow 1$ the $\alpha$-Rényi entropy tends to the [Von Neumann Entropy](#Von_Neumann_Entropy_Equation_target),
\begin{equation}
S(\rho) = \lim_{\alpha \rightarrow 1} S_{\alpha}(\rho).
\end{equation}

:::{dropdown} Properties
:close:
1. $S_\alpha(\rho) \geq 0$ where $S_\alpha(\rho)=0$ iif $\rho$ is a pure state.
2. $ \max_{\rho} S_\alpha(\rho)= \log{d}$ where $d$ is the dimension of the space. This occurs when $\rho$ is maximally mixed. 
3. $S_\alpha(U \rho U^{\dagger}) = S_\alpha(\rho)$ where $UU^{\dagger} = U^{\dagger}U = \mathbb{I}$. 
4. If $\sum_{i} p_i = 1$ then 
\begin{align*} 
S_\alpha \bigg( \sum_{i} p_{i} \rho_i \bigg) \geq \sum_{i} p_{i} S_\alpha(\rho_{i}).
\end{align*} 
5. $S_\alpha(\rho \otimes \sigma) = S_\alpha(\rho) \otimes S_\alpha(\sigma)$.
6. $S_\alpha(\rho) - S_0(\rho_{B}) \leq S_\alpha(\rho_{AB}) \leq S_\alpha(\rho_{A}) + S_0(\rho_{B})$
7. $S_{\alpha_1}(\rho) \geq S_{\alpha_2}(\rho)$ for $1 < \alpha_1 \leq \alpha_2 $.
:::

## Quantum Sandwiched $\alpha$-Rényi Entropies


## Max Relative Entropy 

## Min Relative Entropy 