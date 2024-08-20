---
title: Matrices 
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
keywords: Matrices, Vector Spaces 
abstract: A brief overview of matrices, operations of matrices and other key properties. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

### Matrix Definition 

Let $n,m$ be some integers. An $n \times m$ matrix over a field $\mathbb{F}$ is a rectangular array of numbers $a_{ij}~\in~\mathbb{F}$ with $n$ rows and $m$ columns, such that 
\begin{equation}
A = \begin{pmatrix}
a_{11} & a_{12} & \ldots & a_{1m} \\
a_{21} & a_{22} & \ldots & a_{2m} \\
\vdots & \vdots & \vdots & \vdots \\
a_{n1} & a_{n2} & \ldots & a_{nm} \\
\end{pmatrix}
\end{equation}
The values $a_{ij}$ are called the matrix elements of $A$. 

If $n=m$, the matrix is called a square matrix. 

The $i$th row of $A$ is given by 
\begin{equation}
(a_{i1},~ a_{i2},~ \ldots ~, a_{im}),
\end{equation}
and the $j$th column is given by 
\begin{equation}
\begin{pmatrix}
a_{1m} \\
a_{2m} \\
\vdots  \\
a_{nm}  \\
\end{pmatrix},
\end{equation}
which can be thought of as row and column vectors respectively. The set of $n \times m$ matrices over the field $\mathbb{F}$ is given by $\mathbb{M}_{nm}(\mathbb{F})$.

### Matrix Operations:

::::{tab-set}
:::{tab-item} Scalar Multiplication 
:sync: tab1
Let $A~\in~\mathbb{M}_{nm}(\mathbb{F})$ and $\lambda~\in~\mathbb{F}^{1}$
\begin{equation}
\lambda A = \begin{pmatrix}
\lambda a_{11} & \lambda a_{12} & \ldots & \lambda a_{1m} \\
\lambda a_{21} & \lambda a_{22} & \ldots & \lambda a_{2m} \\
\vdots & \vdots & \vdots & \vdots \\
\lambda a_{n1} & \lambda a_{n2} & \ldots & \lambda a_{nm} \\
\end{pmatrix}
\end{equation}

:::
:::{tab-item} Vector Multiplication
:sync: tab2
Let $A~\in~\mathbb{M}_{nm}(\mathbb{F})$, $\bm{x}, \bm{y}~\in~\mathbb{F}^{m}$ and $\lambda \in \mathbb{F}^{1}$
\begin{equation}
A \bm{x} = \begin{pmatrix}
a_{11} x_1 + a_{12} x_2 + \ldots + a_{1m} x_{m} \\
a_{21} x_1 + a_{22} x_2 + \ldots + a_{2m} x_m\\
\vdots \\
a_{n1} x_1 + a_{n2} x_2 + \ldots + a_{nm} x_m \\
\end{pmatrix} ~\in~\mathbb{F}^{n}
\end{equation}

Hence, one can multiple an $n \times m$ matrix by an vector of length $m$, the output will be a vector of length $n$. 

The $i$th element of the output vector is the dot product between the $i$th row of $A$ and the vector $\bm{x}$. 

**Properties:**
- $A(\bm{x} + \bm{y}) = A\bm{x} + A \bm{y}$
- $A(\lambda)\bm{x} = \lambda A \bm{x}$

:::
:::{tab-item} Matrix Addition
:sync: tab3
Let $A,B~\in~\mathbb{M}_{nm}$
\begin{equation}
A + B = \begin{pmatrix}
a_{11}+b_{11} & a_{12}+b_{12} & \ldots & a_{1m}+b_{1m} \\
a_{21}+b_{21} & a_{22}+b_{22} & \ldots & a_{2m}+b_{2m} \\
\vdots & \vdots & \vdots & \vdots \\
a_{n1}+b_{n1} & a_{n2}+b_{n2} & \ldots & a_{nm}+b_{nm} \\
\end{pmatrix}
\end{equation}
The same logic follows for matrix subtraction. 

::::


::::{tab-set}
:::{tab-item} Transpose
:sync: tab5
Let $A,B~\in~\mathbb{M}_{nm}(\mathbb{F})$, $C~\in~\mathbb{M}_{ml}(\mathbb{F})$, $\bm{x}~\in~\mathbb{F}^{m}, ~\bm{y}~\in~\mathbb{F}^{n}$. 
(tranpose_matrix_operations_target)=
The transpose of $A$, given by $A^{t}~\in~\mathbb{M}_{mn}(\mathbb{F})$, is the matrix obtained by swapping the roles and columns of the matrix $A$. If the matrix element of $A$ in the $i$th row and $j$th column is given by $a_{ij}$, the matrix elements of $A^{t}$ in the $i$th row and $j$th column is given by $a_{ji}$. 

**Properties**: 
- $(AC)^{t} = C^{t}A^{t}$
- $(A+B)^{t} = A^{t} + B^{t} = B^{t} + A^{t}$. 
- $\bm{y} \cdot A \bm{x} = (A^{t}\bm{y}) \cdot \bm{x}$

:::
:::{tab-item} Conjugate transpose
:sync: tab6

Let $A,B~\in~\mathbb{M}_{nm}(\mathbb{C})$, $C~\in~\mathbb{M}_{ml}(\mathbb{C})$.
(conjugate_tranpose_matrix_operations_target)=
The conjugate transpose of $A$, given by $A^{\dagger}~\in~\mathbb{M}_{mn}(\mathbb{C})$, is the matrix obtained by first [transposing](#tranpose_matrix_operations_target) $A$, given by $A^{t}$, and then taking the complex conjugate of all its elements, given by $A^{*}$. This operations can be done is any order, such that $A^{\dagger} = (A^{t})^{*} = (A^{*})^{t}$.

**Properties**: 
- $(AC)^{\dagger} = C^{\dagger}A^{\dagger}$
- $(A+B)^{\dagger} = A^{\dagger} + B^{\dagger} = B^{\dagger} + A^{\dagger}$. 

:::
:::{tab-item} Inverse
:sync: tab7

Let $A,B~\in~\mathbb{M}_{nn}(\mathbb{F})$. 

The matrix $A$ is invertible (non-singular) if there exists a matrix $A^{-1}~\in~\mathbb{M}_{nn}(\mathbb{F})$ such that 
\begin{equation}
A^{-1}A = \mathbb{I},
\end{equation}
where $\mathbb{I}$ is the identity matrix. 

**Properties**
- $(A^{-1})^{-1} = A$
- If $BA=\mathbb{I}$ for some $B$ then $B=A^{-1}$. 
- If both $A$ and $B$ are invertible the $AB$ is invertible with $(AB)^{-1} = B^{-1}A^{-1}$. 

:::
:::{tab-item} Matrix Multiplication
:sync: tab8
Let $A~\in~\mathbb{M}_{nm}$ and $B~\in~\mathbb{M}_{ml}$ and $C=AB$

The elements $c_{ij}$ is given by 
\begin{equation}
c_{ij} = \sum^{m}_{k=1} a_{ik}b_{kj}
\end{equation}
which is the dot product between the $i$th row of A and $j$th column of B. [Elements Form](#elements_view_Matrix_Multiplication_target).

Note the columns of $A$ must equal the rows of $B$ for matrix multiplication to be a valid operation. The output matrix $C$ is then a $n \times l$ matrix, $C~\in~\mathbb{M}_{nl}$. See the below figure for details. 

```{figure} images\LinearAlgebra_matrix_mat_conditions.png
:alt: 
:class: bg-primary
:width: 400px
:align: center
:target: matrix_multplication_condition_target

The conditions on a matrix $A$ and $B$ for them to be compatible for matrix multiplication. The size of the output matrix from the multiplication is shown arising from the size of the input matrices. 
```

**Properties:**
- $AB \neq BA$ in general

Let $A,B~\in~\mathbb{M}_{nm}$ such that $A,B \neq 0$, where $0$ is the zero matrix 
- $\exists~A,B$ such that $AB = 0$, meaning two non-zero matrices can be multiplied to give the zero matrix. Likewise, $\exists ~ A$ such that $A^{2}=AA=0$ for certain $A$. 

Let $A,B~\in~\mathbb{M}_{nm}$ and $C~\in~\mathbb{M}_{ln}$
- $C(A+B) = CA + CB$

Let $A,B~\in~\mathbb{M}_{nm}$ and $C~\in~\mathbb{M}_{ml}$
- $(A+B)C = AC + BC$

Let $A~\in~\mathbb{M}_{nm}$, $B~\in~\mathbb{M}_{ml}$ and $C~\in~\mathbb{M}_{lk}$
- $A(BC) = (AB)C$

:::{dropdown} Elements Form

(elements_view_Matrix_Multiplication_target)=
\begin{align*}
AB = \begin{pmatrix}
a_{11} b_{11} + a_{12} b_{21} + \ldots + a_{1m} b_{m1} & a_{11} b_{12} + a_{12} b_{22} + \ldots + a_{1m} b_{m2} & \ldots \\
a_{21} b_{11} + a_{22} b_{21} + \ldots + a_{2m} b_{m1} & a_{21} b_{12} + a_{22} b_{22} + \ldots + a_{2m} b_{m2} & \ldots \\
\vdots & \vdots & \vdots \\
a_{n1} b_{11} + a_{n2} b_{21} + \ldots + a_{nm} b_{m1} & \ldots & a_{n1} b_{1l} + a_{n2} b_{2l} + \ldots + a_{nm} b_{ml} \\
\end{pmatrix}
\end{align*}
:::

::::


### Matrix Properties 

::::{tab-set}
:::{tab-item} Triangular 
:sync: tab9
Let $A~\in~\mathbb{M}_{nm}$ with elements $a_{ij}$ ($i$th row and $j$th column)

$A$ is upper triangular if $a_{ij}=0$ if $i>j$. For example
\begin{equation}
A = \begin{pmatrix}
1 & 2 & 3 \\
0 & 2 & 4 \\
0 & 0 & 3 \\
\end{pmatrix}
\end{equation}

$A$ is lower triangular if $a_{ij}=0$ if $i<j$. For example
\begin{equation}
A = \begin{pmatrix}
1 & 0 & 0 \\
2 & 4 & 0 \\
3 & 2 & 1 \\
\end{pmatrix}
\end{equation}

:::
:::{tab-item} Symmetric
:sync: tab10
Let $A~\in~\mathbb{M}_{nm}$. 

A is symmetric if $A=A^{t}$ where $(\cdot)^{t}$ is the [transpose operation](#tranpose_matrix_operations_target). 

:::
:::{tab-item} Anti-symmetric 
:sync: tab11

Let $A~\in~\mathbb{M}_{nm}$ with elements $a_{ij}$ ($i$th row and $j$th column)

$A$ is anti-symmetric if $a_{ij} = -a_{ji}$. For example

\begin{equation}
A = \begin{pmatrix}
1 & 2 & -4 \\
-2 & 3 & 5 \\
4 & -5 & 1 \\
\end{pmatrix}
\end{equation}

:::
:::{tab-item} Diagonal 
:sync: tab12

Let $A~\in~\mathbb{M}_{nm}$ with elements $a_{ij}$ ($i$th row and $j$th column)

$A$ is diagonal if $a_{ij} = 0$ if $i \neq j$. 

:::
:::{tab-item} Positive  
:sync: tab13

Let $A~\in~\mathbb{M}_{nm}$ with elements $a_{ij}$ ($i$th row and $j$th column)

$A$ is **positive definite** if for all column vectors $\bm{x}$, 
\begin{equation}
\bm{x}^{*} A \bm{x} > 0,
\end{equation}
where $*$ is the conjugate transpose operation. 

$A$ is **positive semi-definite** if for all column vectors $\bm{x}$, 
\begin{equation}
\bm{x}^{*} A \bm{x} \geq 0. 
\end{equation}

**Negative** and **negative semi-definite** are defined the say way but with inequalities in the opposite direction. 

A matrix is positive definite if it is both hermitian and has all positive eigenvalue - just having positive eigenvalues if not enough for a matrix to be positive definite or positive semi-definite. 

::::
