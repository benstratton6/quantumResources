---
title: Linear Maps 
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
keywords: Linear Maps, Matrices, Vector Spaces 
abstract: A brief overview of maps, the conditions for a map to be a linear maps and some of there properties. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

A map from a vector space $V$ to a vector space $V'$ is a rule which assigns to every element of $V$ an elements in $V'$. 

- A map from a space defined over $\mathbb{F}^{1}$ to $\mathbb{F}^{1}$ is called a function.
- A map from a space defined over $\mathbb{F}^{n}$ to $\mathbb{F}^{1}$ is called a [functional](#functional_target_glossary).
- A map from a space defined over $\mathbb{F}^{n}$ to $\mathbb{F}^{n}$ is called an operator. 

### Linear Map Conditions

A map $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ is called a **linear map** if
- $L(\bm{x} + \bm{y}) = L(\bm{x}) + L(\bm{y})$ forall $\bm{x}, \bm{y} \in \mathbb{F}^{n}$. 
- $L(\lambda \bm{x}) = \lambda L(\bm{x})$ where $\lambda ~ \in ~ \mathbb{F}^{1}$

### Matrices and Linear Maps

Each linear map has an associated matrix. The linear map $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ has an associated matrix $M_{L}~\in~\mathbb{M}_{mn}(\mathbb{F})$ with elements given by 
\begin{equation}
m_{ij} = e^{m}_{i} \cdot L(e^{n}_{j}),
\end{equation}
where $e^{n}_{i}$ and $e^{m}_{j}$ are the [standard basis](#standard_basis_basis_target) of $\mathbb{F}^{n}$ and $\mathbb{F}^{m}$ respectively. 

The map $L$ can be applied to a vector $\bm{x} \in \mathbb{F}^{n}$ via its associated matrix as 
\begin{equation}
L(\bm{x}) = M_{L} \bm{x}~\in~\mathbb{F}^{m}.
\end{equation}

### Operations of Linear Maps

::::{tab-set}
:::{tab-item} Scalar Multiplication
:sync: tab1
Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be a linear map with associated matrix $M_{L}~\in~\mathbb{M}_{mn}(\mathbb{F})$ and $\lambda~\in~\mathbb{F}^{1}$

\begin{equation}
(\lambda L)(\bm{x}) = \lambda L(\bm{x})
\end{equation}

where $\lambda L$ is also a linear map. 

On the associated matrix $M_{L}$ with elements $m_{ij}$ this becomes 
\begin{equation}
M_{\lambda L} = \lambda M_{L} = \lambda m_{ij}.
\end{equation}

:::

:::{tab-item} Addition
:sync: tab2
Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ and $T: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be linear maps with associated matrices $M_{L}~\in~\mathbb{M}_{mn}(\mathbb{F})$ and $M_{T}~\in~\mathbb{M}_{mn}(\mathbb{F})$, and $\bm{x} \in \mathbb{F}^{n}$. 

The addition of $L$ and $T$ is defined as 
\begin{equation}
(L+T)(\bm{x}) = L(\bm{x}) + T(\bm{x}),
\end{equation}
where $L+T$ is also a linear map. 

On the associated matrices $M_{L}$ and $M_{T}$ with elements $m_{ij}$ and $t_{ij}$ respectively, this becomes 
\begin{equation}
M_{L+T} = (m_{ij} + t_{ij}) = M_{L} + M_{T}. 
\end{equation}
:::
:::{tab-item} Concatenations
:sync: tab3
Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ and $R,T: \mathbb{F}^{m} \rightarrow \mathbb{F}^{k}$ be linear maps.

\begin{equation}
(R + T) \circ L = R \circ L + T \circ L.
\end{equation}

Let $L,R: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ and $T: \mathbb{F}^{m} \rightarrow \mathbb{F}^{k}$ be linear maps.

\begin{equation}
T \circ (L + R) = T \circ L + T \circ R.
\end{equation}

Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$, $R: \mathbb{F}^{m} \rightarrow \mathbb{F}^{k}$ and $T: \mathbb{F}^{k} \rightarrow \mathbb{F}^{q}$ be linear maps.

\begin{equation}
  (T \circ R) \circ L = T \circ (R \circ L).
\end{equation}

Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ and $R: \mathbb{F}^{m} \rightarrow \mathbb{F}^{k}$ be linear maps with associated matrices $M_{L}~\in~\mathbb{M}_{mn}(\mathbb{F})$ and $M_{R}~\in~\mathbb{M}_{km}(\mathbb{F})$.

If $T = R \circ L$ is a linear map then $M_{T} = M_{R}M_{L}~\in~\mathbb{M}_{kn}(\mathbb{F})$. 
:::
:::{tab-item} Image and Kernel
:sync: tab4

Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be a linear map.

The **image** of L is defined to be 
\begin{equation}
\textrm{Im}L \coloneqq \{ \bm{y} \in \mathbb{F}^{m} : ~ \exists ~\bm{x}~\in~\mathbb{F}^{n}~\textrm{where}~L(\bm{x}) = \bm{y} \} \subset \mathbb{F}^{m}.
\end{equation}
These are the possible output vectors or the linear map.

The **kernel** of L is defined to be 
(kernal_linear_maps_target)=
\begin{equation}
\textrm{Ker} L \coloneqq \{\bm{x} \in \mathbb{F}^{n} : L(\bm{x}) = 0 \} \subset \mathbb{F}^{n}.
\end{equation}
These are the input vectors for which the linear map returns the zero vector. 


:::
::::

### Properties of Linear Maps

::::{tab-set}
:::{tab-item} Surjective
:sync: tab5
Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be a linear map.

$L$ is surjective if and only if
(Surjective_linear_maps_target)=
\begin{equation}
\textrm{Im}L = \mathbb{F}^{m},
\end{equation}
meaning the map can output all possible vectors in the output space. 

:::
:::{tab-item} Injective
:sync: tab6
Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be a linear map.

$L$ is injective if and only if
(injective_linear_maps_target)=
\begin{equation}
\textrm{Ker}L = \{ \bm{0} \},
\end{equation}
where $\bm{0}$ is the zero vector. 

This means the only input vector the map can output $\bm{0}$ for is $\bm{0}$. 
:::
:::{tab-item} Bijective 
:sync: tab7
Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be a linear map.

$L$ is bijective if it is both [surjective](#Surjective_linear_maps_target) and [injective](#injective_linear_maps_target). 

**Properties:**
- Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{n}$ be a linear map and bijective, $L^{-1}: \mathbb{F}^{n} \rightarrow \mathbb{F}^{n}$ be also a linear map, where $L^{-1}$ is the inverse map. 

:::
:::{tab-item} Nullity 
:sync: tab8

Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be a linear map.

The nullity of $L$ is defined to be 
\begin{equation}
\textrm{nullity} L \coloneqq \textrm{dim} ~\textrm{Ker} L.
\end{equation} 

where $\textrm{dim}$ is the [dimension](#dimension_vector_spaces_target). 
:::
:::{tab-item} Rank 
:sync: tab9

Let $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ be a linear map.

The rank of $L$ is defined to be 
(rank_target_linear_maps)=
\begin{equation}
\textrm{rank} L \coloneqq \textrm{dim} ~\textrm{Im} L.
\end{equation} 

where $\textrm{dim}$ is the [dimension](#dimension_vector_spaces_target). 

::::

### Projections
(projections_linear_maps_target)=
A linear map $L: V \rightarrow V$ is a projection if $L^{2}=L$. 

This means applying the map twice gives the same results as applying the map once. 

#### Properties of Projections

Let $L: V \rightarrow V$ be a projection.

- $u~\in~\textrm{Im}P ~ ~ \textrm{iif} ~ ~ Pu=v$.
- $V = \textrm{Ker} V \oplus \textrm{Im} V$ if $V$ is finite dimensional.

