---
title: The Adjoint
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
keywords: Vectors, Vector Spaces, Inner Products, Adjoint, Transpose, Complex Conjugate. 
abstract: The definition of the adjoint operator.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

### Adjoint Definition 

Let $V$ be an inner product space defined over $\mathbb{C}$, with inner product $(\cdot, \cdot): \mathbb{C}^{n} \otimes \mathbb{C}^{n} \rightarrow \mathbb{C}^{1}$, and $L: V \rightarrow V$ a linear operator. 
(the_adjoint_definition_target)=
The **adjoint operator** of the linear operator $L$, denoted by $L^{\dagger}$, is the operator that satisfies the following relation 
\begin{equation}
(L^{\dagger}(\bm{x}), \bm{y}) = (\bm{x}, L(\bm{y})),
\end{equation}
where $\bm{x}, \bm{y}~\in~V$.

### Associated Matrix of the Adjoint

Let $M^{\mathfrak{B}}_{L}$ be the matrix associated to the linear map $L$ with respect to the orthonormal basis $\mathfrak{B}$ and the element in the $i$th row and $j$th colunm be $a_{ij}$. 

The matrix associated to the linear map $L^{\dagger}$ with respect to the orthonormal basis $\mathfrak{B}$, $M_{L^{\dagger}}^{\mathfrak{B}}$, is given by taking the complex conjugate of all elements of $M_{L}^{\mathfrak{B}}$ and then transposing. Hence, the element in the $i$th row and $j$th column of $M_{L^{\dagger}}^{\mathfrak{B}}$ will be $a^{*}_{ji}$.

For this reason, the adjoint is also sometimes referred to as the conjugate transpose operations. 

### Properties of the Adjoint

Let $V, (\cdot, \cdot)$ be an inner product space defined over $\mathbb{C}$, let $L, T: V \rightarrow V$ be linear operators and $\lambda~\in~\mathbb{C}^{1}$. 

- $(L+T)^{\dagger} = L^{\dagger} + T^{\dagger}$. 
- $(\lambda L)^{\dagger} = \lambda^{*} L^{\dagger}$, where $(\cdot)^{*}$ is the complex conjugate. 
- $(LT)^{\dagger} = T^{\dagger}L^{\dagger}.$
- $(L^{\dagger})^{\dagger} = L$. 
- If $L^{-1}$ exists, then $(L^{\dagger})^{-1} = (L^{-1})^{\dagger}$.


### Matrix Properties From the Adjoint

::::{tab-set}
:::{tab-item} Unitary  
:sync: tab1

Let $A~\in~\mathbb{M}_{nm}$. 

$A$ is unitary if $A^{\dagger}A=AA^{\dagger}=\mathbb{I}$,

where $\mathbb{I}$ is the identity. 

**Properties** 

Let $A$ be unitary, then: 

- $A^{-1}$ is unitary. 
- $\vert \vert U \bm{x} \vert \vert = \vert \vert \bm{x} \vert \vert$, where $\bm{x}~\in~V$ and $\vert \vert \cdot \vert \vert$ is a [norm](#norms_page_target).
- If $ \lambda $ is an [eigenvalue](#eigenvalues_page_target) of $A$, then $\vert \lambda \vert = 1$, meaning $A$ has complex eigenvalues of magnitude one.  
- The columns of $A$ form an [orthonormal basis](#Orthonormal_Basis_basis_target). 
:::
:::{tab-item} Hermitian
:sync: tab2
Let $A~\in~\mathbb{M}_{nm}$. 

$A$ is hermitian, or self-adjoint, if $A=A^{\dagger}$.

**Properties** 

Let $A$ be hermitian, then: 

- $A$ has only real [eigenvalues](#eigenvalues_page_target). 
- $A$'s eigenvectors with different eigenvalues are orthogonal.

:::
:::{tab-item} Normal 
:sync: tab3

Let $A~\in~\mathbb{M}_{nm}$. 

$A$ is normal if $A^{\dagger}A = AA^{\dagger}$

**Properties** 

Let $A$ be normal, then:

- If $ A\bm{x} = \lambda \bm{x} $ such that $ \lambda $ is an [eigenvalue](#eigenvalues_page_target) of $A$, then
\begin{equation}
A^{\dagger} \bm{x} = \lambda^{*} \bm{x},
\end{equation}
where $\lambda^{*}$ is the complex conjugate of $ \lambda $ and $\bm{x}~\in~V$.
- $A$'s eigenvectors with different eigenvalues are orthogonal.
- The space in which $A$ is defined over will have an orthonormal basis of eigenvectors of $A$.
- There exists a unitary matrix, $U$, that can diagonalise $A$, 
\begin{equation}
U^{\dagger}AU = \begin{pmatrix}
\lambda_{1} & 0 & \ldots & 0 \\
0 & \lambda_{2} & \ldots & 0 \\
\vdots & \vdots & \vdots & \vdots \\
0 & 0 & \ldots & \lambda_n \\
\end{pmatrix},
\end{equation} 
where $\textrm{Spec}A = (\lambda_1, \ldots, \lambda_n)$. The matrix $U$ will have the eigenvectors of $A$ as its columns. 
::::
