---
title: Stochastic Matrices
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
keywords: Matrices. 
abstract: The conditions for a matrix to be stochastic. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(stocastic_matrices_mathnotes_target)=
A stochastic matrix, $A$, is a square matrices with positive real values as elements, $A \in \mathbb{M}_{nn}(\mathbb{R^{+}})$. Each element represents the probability of some transformation taking place. 

They are applied to vectors that contain probabilities of a system being in a given state. For example, 
\begin{equation}
\bm{p} = (p_{1}, p_2, \ldots, p_{n}) ~ ~ \textrm{where} ~ ~ p_{i}\geq0~\forall~i ~, \sum_{i}^{n} p_{i} = 1,
\end{equation}
and $p_{i}$ is the probability of they system being in the $i$th state.  

- $A$ is left stochastic if each row sums to one. 
- $A$ is right stochastic if each column sums to one. 
- $A$ is doubly stochastic if each row and column sums to one. This means both $A$ and $A^{t}$ are stochastic matrices. 

If 
\begin{equation}
A = \begin{pmatrix}
a_{11} & a_{12} & \ldots & a_{1n} \\
a_{21} & a_{22} & \ldots & a_{2n} \\
\vdots & \vdots & \vdots & \vdots \\
a_{n1} & a_{n2} & \ldots & a_{nn} \\
\end{pmatrix},
\end{equation}
then $a_{11}$ is the probability of initially being in the $1$ state and ending up in the $1$ state,  $a_{12}$ is the probability of initially being in the $1$ state and ending up in the $2$ state etc.. 

The total probability that a state starts in a given state and ends up in another must be one, hence
\begin{equation}
\sum_{j=1}^{n}a_{ij} = 1,
\end{equation}
and $A$ is left stochastic. 

### Fixed Points

Let $A$ be a left stochastic matrix and $\bm{p}$ be a probability vector such that 
\begin{equation}
\bm{p}A = \bm{p},
\end{equation}
then $\bm{p}$ is the stationary probability vector, or fixed point, of the transformation $A$. 

All doubly stochastic matrices have the maximally mixed probability vector as there fixed point, such that
\begin{equation}
(1/n, 1/n, \ldots, 1/n) A = (1/n, 1/n, \ldots, 1/n),
\end{equation}
if $A$ is doubly stochastic. 

If there exists a stocastic matrix $A$ such that $\bm{p}A = \bm{p'}$, then $\bm{p'}$ can be considered to be *more mixed* then $\bm{p}$.

### Birkhoff-Von Neumann Theorem
(double_stocastic_matrix_mathNotes_target)=
$A \in \mathbb{M}_{nn}(\mathbb{R^{+}})$ is a doubly stochastic matrix if and only if there exists a set of numbers $\{p_{i}\}$ where $p_i \geq 0~\forall~i$ and $\sum_k p_{k} = 1$ such that 
\begin{equation}
A = \sum_{i} p_{i} V_{i},
\end{equation}
where $V_{i} \in \mathbb{M}_{nn}(\mathbb{R^{+}})$ are the $n \times n$ [permutation matrices](https://en.wikipedia.org/wiki/Permutation_matrix). Therefore, all doubly stochastic matrices are convex combinations of permutation matrices.  