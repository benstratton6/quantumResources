---
title: Eigenvectors and Eigenvalues
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
keywords: Eigenvectors, eigenvalues, vector spaces, linear maps. 
abstract: A brief overview of eigenvectors and eigenvalues.   
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(eigenvalues_page_target)=
### Definition
(eigenvalues_definition_target_eigenvalues)=
Let $V$ be a vector space defined over a field $\mathbb{F}$ and $L: V \rightarrow V$ be a linear map. A vector $\bm{v}~\in~V$, where $\bm{v} \neq 0$, is called an **eigenvector** of the map $L$ if 
\begin{equation}
L(\bm{v}) = \lambda \bm{v},
\end{equation}
where $\lambda~\in~\mathbb{F}^{1}$ is the **eigenvalue** of the eigenvector $\bm{v}$.

The set of all eigenvalues of a linear map $L$ is called the spectrum of $L$, denoted $\textrm{spec}L$. 

An vector space is said to be degenerate if different eigenvectors have the same eigenvalue.  

### Basis of Eigenvectors

Let $L: V \rightarrow V$ be linear map, where $V$ is a vector space of dimension $n$. The space $V$ can have a basis that consists of vectors of eigenvectors of $L$, say $\{\bm{v}_1, \bm{v}_2, \ldots, \bm{v}_n \}$ with eigenvalues $\{\lambda_1, \lambda_2, \ldots, \lambda_n \}$ - such that $L(\bm{v}_{i}) = \lambda_i \bm{v}_i$. 

If so, then the matrix associated to the linear map $L$, $M_{L}$, can be written with respect to this basis as 
\begin{equation}
M_{L} = \begin{pmatrix}
\lambda_{1} & 0 & \ldots & 0 \\
0 & \lambda_{2} & \ldots & 0 \\
\vdots & \vdots & \vdots & \vdots \\
0 & 0 & \ldots & \lambda_n \\
\end{pmatrix}.
\end{equation}

This also works the other way around. If there exists a basis, $\{\bm{v}_1, \bm{v}_2, \ldots, \bm{v}_n \}$, such that $M_{L}$ can be written diagonally (as above) then vectors in the basis are eigenvectors of $L$ and the associated value on the diagonal is the eigenvalues. 

**Conditions on a Basis of Eigenvectors**

::::{tab-set}
:::{tab-item} Condition 1
:sync: tab1
Let $L:V \rightarrow V$ be a linear operator, where $V$ is a vector space of $\textrm{dim}V=n$. 

The vector space $V$ has a basis of eigenvectors if and only if $V$ can be decomposed into a [direct sum](#direct_sum_vector_spaces) of eigenspaces
\begin{equation}
V = V_{\lambda_1} \oplus V_{\lambda_2} \oplus \ldots \oplus V_{\lambda_n}.
\end{equation}
:::
:::{tab-item} Condition 2
:sync: tab2
Let $L:V \rightarrow V$ be a linear operator, where $V$ is a vector space of $\textrm{dim}V=n$.

If $L$ has $n$ *different* eigenvalues, then it has a basis of eigenvectors. 
:::
:::{tab-item} Condition 3
:sync: tab3

Let $L:V \rightarrow V$ be a linear operator, where $V$ is a vector space of $\textrm{dim}V=n$, and $\{\bm{v}_1, \bm{v}_2, \ldots, \bm{v}_n \}$ a set of eigenvectors with *different* eigenvalues. 

The set $\{\bm{v}_1, \bm{v}_2, \ldots, \bm{v}_n \}$ is [linear independent](#linearly_independent_target). 

::::

### Calculating Eigenvectors and Eigenvalues

Let $L:V \rightarrow V$ be a linear operator, where $V$ is a vector space of $\textrm{dim}V<\infty$ defined over $\mathbb{F}$. 

$\lambda~\in~\mathbb{F}^{1}$ is an eigenvector of $L$ if and only if 
\begin{equation}
\textrm{Det}(M_{L} - \lambda \mathbb{I}) = 0,
\end{equation}
where $\textrm{Det}$ is the [determinant](https://en.wikipedia.org/wiki/Determinant) and $M_L$ is the matrix associated to $L$ (note this is independent of the choice of basis for $M_L$). 

One can define the *characteristic polynomial* of $L$ as $P(\lambda)=\textrm{Det}(M_{L} - \lambda \mathbb{I})$, the roots of the characteristic polynomial then give the eigenvalues of $L$. 

The corresponding eigenspace to an eigenvalues $ \lambda $ is then given by 
\begin{equation}
V_{\lambda} = \textrm{Ker}(M_{L} - \lambda \mathbb{I}),
\end{equation}
where $\textrm{Ker}$ is the [kernel](#kernal_linear_maps_target).

### Real Matrices 

Let $M~\in~\mathbb{M}(\mathbb{R})$ be symetric, $M^{t}=M$, then there exists a matrix $B~\in~\mathbb{M}(\mathbb{R})$ such that 
\begin{equation}
B^{t}MB = \begin{pmatrix}
\lambda_{1} & 0 & \ldots & 0 \\
0 & \lambda_{2} & \ldots & 0 \\
\vdots & \vdots & \vdots & \vdots \\
0 & 0 & \ldots & \lambda_n \\
\end{pmatrix},
\end{equation}
where $\{ \lambda_1, \lambda_2, \ldots, \lambda_n \}$ are eigenvalues of $M$ and $B$ has an [orthonormal basis](#Orthonormal_Basis_basis_target) of eigenvectors as its columns such that $B^{t}B=\mathbb{I}$. 


### Further Properties

::::{tab-set}
:::{tab-item} Determinant
:sync: tab4
Let $L:V \rightarrow V$ be a linear operator, where $V$ is a vector space of $\textrm{dim}V=n$ defined over $\mathbb{F}^{1}$, with eigenvalues $\{\lambda_1, \lambda_2, \ldots, \lambda_n \}$ that are not necessarily distinct. 

The [determinant](https://en.wikipedia.org/wiki/Determinant) of $L$ is given by 
\begin{equation}
\textrm{Det}L = \prod^{n}_{i} \lambda_i.
\end{equation}
:::
:::{tab-item} Trace
:sync: tab5
Let $L:V \rightarrow V$ be a linear operator, where $V$ is a vector space of $\textrm{dim}V=n$ defined over $\mathbb{F}^{1}$, with eigenvalues $\{\lambda_1, \lambda_2, \ldots, \lambda_n \}$ that are not necessarily distinct. 

The [trace](https://en.wikipedia.org/wiki/Trace_(linear_algebra)) of $L$ is given by 
\begin{equation}
\textrm{tr}L = \sum^{n}_{i} \lambda_i.
\end{equation}
:::
::::

### Further Resource

- 3Blue1Brown Video: [Eigenvectors and eigenvalues | Chapter 14, Essence of linear algebra](https://www.youtube.com/watch?v=PFDu9oVAE-g&ab_channel=3Blue1Brown)