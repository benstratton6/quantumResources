---
title: Vectors 
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
keywords: Vectors, dot product, cross product. 
abstract: A very brief overview of vectors, operations of vectors and other key properties. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Vectors Definition 

A vector is a collection of elements from a given field $\mathbb{F}$. This field could be the real numbers, $\mathbb{R}$, or the complex number, $\mathbb{C}$, for example. Vectors are often written in columns such as 
(vector_example)=
\begin{equation}
    \bm{x} &= \begin{bmatrix}
           x_{1} \\
           x_{2} \\
           \vdots \\
           x_{n}
         \end{bmatrix},
  \end{equation}
where each component $x_{i}$ is a element in $\mathbb{F}$. This vector is an $n$ dimensional vector over the field $\mathbb{F}$, which we can write as $\bm{x} \in \mathbb{F}^{n}$, meaning $\bm{x}$ is a vector of $n$ components where each components is from the field $\mathbb{F}$. 

## Vector Operations:

::::{tab-set}
:::{tab-item} Vector Addition
:sync: tab1
let $\bm{x} \in \mathbb{F}^{n}, ~\bm{y} \in \mathbb{F}^{n}$ 

\begin{equation}
    \bm{x} + \bm{y} = \begin{bmatrix}
           x_{1} + y_{1} \\
           x_{2} + y_{2} \\
           \vdots \\
           x_{n} + y_{n}
         \end{bmatrix}
\end{equation}
:::
:::{tab-item} Scalar Multiplication
:sync: tab2
let $\bm{x} \in \mathbb{F}^{n}, ~ \bm{y} \in \mathbb{F}^{n},~ \lambda \in \mathbb{F}^{1}$

\begin{equation}
    \lambda \bm{x} = \begin{bmatrix}
           \lambda x_{1} \\
           \lambda x_{2} \\
           \vdots \\
           \lambda x_{n}
         \end{bmatrix},
\end{equation}

Hence, $\lambda (\bm{x} + \bm{y}) = \lambda \bm{x} + \lambda \bm{y}$
:::
:::{tab-item} Dot Product
:sync: tab3
let $\bm{x} \in \mathbb{F}^{n}, ~\bm{y} \in \mathbb{F}^{n}, ~\bm{v} \in \mathbb{F}^{n},~ \lambda \in \mathbb{F}^{1}$ 

\begin{equation}
    \bm{x} \cdot \bm{y} = x_{1}y_{1} + x_{2}y_{2} \ldots x_{n}y_{n}
\end{equation}

**Properties:**

- $\bm{x} \cdot \bm{y} = \bm{y} \cdot \bm{x}$
- $\bm{x} \cdot (\bm{y} + \bm{v}) = \bm{x} \cdot \bm{y} + \bm{x} \cdot \bm{v}$
- $(\bm{x} + \bm{y}) \cdot \bm{v} = \bm{x} \cdot \bm{v} + \bm{y} \cdot \bm{v}$
- $(\lambda \bm{x}) \cdot \bm{y} = \lambda(\bm{x} \cdot \bm{y}) = \bm{x} \cdot (\lambda \bm{y})$
:::
:::{tab-item} Cross Product 
:sync: tab4
let $\bm{x} \in \mathbb{F}^{n}, ~\bm{y} \in \mathbb{F}^{n}, \bm{v} \in \mathbb{F}^{n}, ~ \lambda \in \mathbb{F}^{1}$

\begin{equation}
\bm{x} \times \bm{y} = \vert \vert \bm{x} \vert \vert ~ \vert \vert \bm{y} \vert \vert \textrm{sin}(\theta) \bm{\hat{m}}
\end{equation}

where $\theta$ is the angle between $\bm{x}$ and $\bm{y}$, and $\bm{\hat{m}}$ is a unit vector perpendicular to both $\bm{x}$ and $\bm{y}$. 

**Properties:**

- $\bm{x} \times \bm{x} = 0$
- $\bm{x} \times \bm{y} = - \bm{y} \times \bm{x}$
- $(\lambda \bm{x}) \times \bm{y} = \bm{x} \times (\lambda \bm{y}) = \lambda (\bm{x} \times \bm{y})$
- $\bm{x} \times (\bm{y} \times \bm{v}) + \bm{y} \times (\bm{v} \times \bm{x}) + \bm{v} \times (\bm{x} \times \bm{y}) = 0$
::::

::::{tab-set}
:::{tab-item} Vector Norm
:sync: tab5
Let $\bm{x} \in \mathbb{F}^{n}, ~ \lambda \in \mathbb{F}^{1}$

\begin{equation}
\vert \vert \bm{x} \vert \vert = \bigg( \sum^{n}_{i} x_{i}^{2} \bigg)^{1/2}
\end{equation}

**Properties:**

- $\vert \vert \bm{x} \vert \vert \geq 0, ~\textrm{where}~\vert \vert \bm{x} \vert \vert = 0 ~\textrm{iif.}~\bm{x}=0$
- $\vert \vert \lambda \bm{x} \vert \vert = \vert \lambda \vert ~ \vert \vert \bm{x} \vert \vert$
- $ \vert \vert \bm{x} + \bm{y} \vert \vert \leq \vert \vert \bm{x} \vert \vert + \vert \vert \bm{y} \vert \vert$

This is just one example of a vector norm. See more on the [norms page](#norms_page_target)
:::
:::{tab-item} Orthogonality
:sync: tab6
let $\bm{x} \in \mathbb{F}^{n}, ~\bm{y} \in \mathbb{F}^{n}$

$\bm{x}$ and $\bm{y}$ are orthogonal if $\bm{x} \cdot \bm{y} = 0$.
:::
:::{tab-item} Span
:sync: tab7

let $\bm{x} \in \mathbb{F}^{n}, ~\bm{y} \in \mathbb{F}^{n}$
(span_definition_target)=
$\textrm{span} \{ \bm{x},\bm{y} \} := \{\lambda_1 \bm{x} + \lambda_2 \bm{y} : \forall~ \lambda_1, \lambda_2 \in \mathbb{F}^{1} \}$

The span of a set of vectors is therefore the set of all possible linear combinations of the vectors in the set. 
::::

## Vector Properties 

::::{tab-set}
:::{tab-item} Pythagoras' Theorem
:sync: tab1
let $\bm{x} \in \mathbb{F}^{n}, ~\bm{y} \in \mathbb{F}^{n}$

\begin{equation}
\vert \vert \bm{x} + \bm{y} \vert \vert^{2} = \vert \vert \bm{x} \vert \vert^{2} + \vert \vert \bm{y} \vert \vert^{2}
\end{equation}
:::
:::{tab-item} Cauchy-Schwarz Inequality
:sync: tab2
let $\bm{x} \in \mathbb{F}^{n}, ~\bm{y} \in \mathbb{F}^{n}$

\begin{equation}
\vert \bm{x} \cdot \bm{y} \vert \leq \vert \vert \bm{x} \vert \vert ~\vert \vert \bm{y} \vert \vert 
\end{equation}
::::

