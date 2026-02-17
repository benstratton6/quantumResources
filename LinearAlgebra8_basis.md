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
(basis_page_target)=
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
(Orthonormal_Basis_basis_target)=
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

### Tensor Product Basis 

Let the set of vectors $\{ a_i \}_i$ be a basis of the space $\mathcal{A}$, and the set of vectors $\{ b_j \}_j$ be a basis of the space $\mathcal{B}$.

Then the set of vectors $\{ a_i \otimes b_j\}_{i,j}$ are a basis of the space $\mathcal{A} \otimes \mathcal{B}$. 

:::{dropdown} Proof
:open:

A general element of the space $\mathcal{A} \otimes \mathcal{B}$, denoted $V$, is 
\begin{equation}
V = \sum_k c_k v^k \otimes u^k,
\end{equation} 
where 
\begin{equation}
c_k \in \mathbb{C}, v^k \in \mathcal{A}, u^k \in \mathcal{B} ~\forall~k.
\end{equation}
Given $v_k \in \mathcal{A}$ and the fact that $\{ a_i \}_i$ is a basis for $\mathcal{A}$, there exists a set of complex coefficients $\{\alpha^k_i : \alpha^k_i \in \mathbb{C} \}_i$ such that 
\begin{equation}
v^k = \sum_i \alpha^k_i a_i.
\end{equation}
The same holds for $u^k \in \mathcal{B}$ i.e., there exists a set of complex coefficients, $\{\beta^k_i : \beta^k_i \in \mathbb{C} \}_i$ such that 
\begin{equation}
u^k = \sum_i \beta^k_i b_i.
\end{equation}
:::
