---
title: Vector Spaces
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
keywords: Vectors, Vector Spaces
abstract: The conditions for a vector space. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

A vector space, defined over a field $\mathbb{F}$, is a set $V$ whose elements can be added together and multiplied by a scalars ($\mathbb{F}^{1}$). The elements of $V$, whilst often called vectors, can be a variety of different mathematical objects, such as [vectors](#vector_example) in the typical sense, or matrices. 

Vector spaces defined over $\mathbb{R}$ are known as real vector spaces, whilst vector spaces defined over $\mathbb{C}$ are defined as complex vector spaces. 

## Vector Space Axioms
Let $\psi, ~\sigma, ~\omega~\in~V$ and $a,b \in \mathbb{F}^{1}$.

(vector_space_axioms_target)=
In order for $V$ to be a vector space, the addition and scalar multiplication operations must meet a set of Axioms, defined below.

The addition operation must obey the following conditions 

1. $~~\psi + \sigma = \sigma + \psi$
    - Commutativity
2. $\psi + (\sigma + \omega) = (\psi + \sigma) + \omega$
    - Associativity
3. $\exists ~I \in ~V$ such that $\psi + I = \psi$.
    - Identity
4. $~~\forall~v~\in~V, \exists -v~\in~V$ such that $v+-v=I$.
    - Inverse

The multiplication by a scalar operation must obey the following conditions 
1. $a(\psi + \omega) = a \psi + b \omega$
    - distributive over $V$
2. $(a+b)\psi = a\psi + b\psi$
    - distributive over scalar


## Further Vector Space Properties 
::::{tab-set}
:::{tab-item} Linear Combination
:sync: tab1
Let $a_{1}, ~a_{2}, \ldots ~a_{n}~\in~V~\forall~n$ and $\lambda_1,~\lambda_2, \ldots ~\lambda_n~\in~\mathbb{F}^{1} ~\forall~n$
(linear_combination_Vector_space_target)=
A linear combination of the vectors $\{ a_{1}, ~a_{2}, \ldots, ~a_{n} \} $ is given by

\begin{equation}
\tilde{a} = \lambda_1 a_{1} + \lambda_2 a_2 \ldots \lambda_n a_n
\end{equation}
All linear combinations of vectors in $V$ are also in V, $\tilde{a}~\in~V$. 
:::
:::{tab-item} Linear (In)dependence
:sync: tab2
Let $a_{1}, ~a_{2}, \ldots ~a_{n}~\in~V~\forall~n$ 

**linearly dependent:** The set of vectors $\{ a_{1}, ~a_{2}, \ldots, ~a_{n} \} $ are linearly dependent if there exists $\lambda_1,~\lambda_2, \ldots ~\lambda_n~\in~\mathbb{F}^{1}$, where $\lambda_{j}$ is not equal to $0$ for all $n$, such that 
\begin{equation}
\lambda_1 a_{1} + \lambda_2 a_2 \ldots \lambda_n a_n = 0
\end{equation}

(linearly_independent_target)=
**linearly independent:** The set of vectors $\{ a_{1}, ~a_{2}, \ldots, ~a_{n} \} $ are linearly independent if there does not exists $\lambda_1,~\lambda_2, \ldots ~\lambda_n~\in~\mathbb{F}^{1}$ such that 
\begin{equation}
\lambda_1 a_{1} + \lambda_2 a_2 \ldots \lambda_n a_n = 0
\end{equation}
unless $\lambda_{j}$ is equal to $0$ for all $n$.
:::
:::{tab-item} Linear Subspace
:sync: tab3
Let $G \subset V$ 

$G$ is a linear subspace of $V$ if 
1. $G \neq \varnothing$, 
    - the set $G$ is not empty 
2. $\forall~\psi, \sigma \in G$ it is true that $\psi + \sigma \in G$, 
    - $G$ is closed under addition.
3. $\forall~\psi,~~ \lambda \in \mathbb{F}^{1}$ it is true that $\lambda \psi \in G$, 
    - $G$ is closed under multiplication.
:::
:::{tab-item} Basis
:sync: tab4
Let $a_{1}, ~a_{2}, \ldots, ~a_{n}~\in~V~\forall~n$ 
(basis_vector_space_target)=
The set of vectors $\{ a_{1}, ~a_{2}, \ldots, ~a_{n} \} $ are a basis of $V$ if 
1. $\textrm{Span}(\{ a_{1}, ~a_{2}, \ldots ~a_{n} \}) = V$
    - Any vectors in $V$ can written as a linear combination of the vectors in $\{ a_{1}, ~a_{2}, \ldots ~a_{n} \} $ [💭](#span_definition_target). 
2. The vectors $\{ a_{1}, ~a_{2}, \ldots ~a_{n} \} $ are [linear independent](#linearly_independent_target_glossary).  
:::
::::



