---
title: Basis
subject: Tutorial
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
keywords: Vectors, Vector Spaces, basis
abstract: The conditions for a set of vectors to be a basis and some properties of vector basis.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

### Basis Conditions

(basis_basis_target)=
Let $V$ be a vector space and $a_{1}, ~a_{2}, \ldots, ~a_{n}~\in~V~\forall~n$.  

The set of vectors $\{ a_{1}, ~a_{2}, \ldots, ~a_{n} \} $ are a basis of $V$ if 
1. $\textrm{Span}(\{ a_{1}, ~a_{2}, \ldots ~a_{n} \}) = V$
    - Any vectors in $V$ can written as a linear combination of the vectors in $\{ a_{1}, ~a_{2}, \ldots ~a_{n} \} $ [💭](#span_definition_target). 
2. The vectors $\{ a_{1}, ~a_{2}, \ldots ~a_{n} \} $ are [linear independent](#linearly_independent_target_glossary).  

### Use of Basis

For any $\psi~\in~V$, if $\{ a_{1}, ~a_{2}, \ldots, ~a_{n} \} $ forms a basis, there exists a unique set of scalars $\lambda_{1}, \lambda_2, \ldots, \lambda_{n}~\in~\mathbb{F}^{n}$ such that 
\begin{equation}
\psi = \lambda_{1} a_{1} + \lambda_2 a_{2} + \ldots + \lambda_{n} a_{n}.
\end{equation}
Hence, given a basis one can write any vector in the space as a sum over those vectors in the basis.  

### Basis Properties 

- All linear subspaces of a vector space have a basis. 
- All basis of a given subspace have the same number of elements.  

### Special Basis 

::::{tab-set}
:::{tab-item} Standard Basis
:sync: tab1
let $V$ be a vector space defined over $\mathbb{F}^{n}$.

The **standard basis** of a vector space $V$ is given by 
(standard_basis_basis_target)=
\begin{equation}
e_{1} &= \begin{bmatrix}
           1 \\
           0 \\
           \vdots \\
           0
         \end{bmatrix}, ~ ~ 
e_2 &= \begin{bmatrix}
0 \\
1 \\
\vdots \\
0
\end{bmatrix}, ~~ 
e_n &= \begin{bmatrix}
    0 \\
    0 \\
    \vdots \\
    1
    \end{bmatrix}.
\end{equation}

:::
:::{tab-item} Orthonormal Basis 
:sync: tab2
Let the set of vectors $\{ a_{1}, ~a_{2}, \ldots, ~a_{n} \} $ be a basis of a vector space $V$. This basis is an orthonormal basis if 
\begin{equation}
a_{i} \cdot a_{j} = \delta_{ij},
\end{equation}
where $\delta_{ij}$ is the [Kronecker delta function](https://en.wikipedia.org/wiki/Kronecker_delta) given by 
\begin{equation}
\delta_{ij} \coloneqq \left\{
	\begin{array}{ll}
		1  & \mbox{if } i = j \\
		0 & \mbox{if } i \neq j
	\end{array}
\right.
\end{equation}
:::
::::

