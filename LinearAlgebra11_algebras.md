---
title: Algebras
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
keywords: Vectors, Vector Spaces, Algebra. 
abstract: The definition an algebra.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(alebra_page_target)=
### Algebra Definition 

Let $\mathbb{F}$ be a field over which a [vector space](#vector_space_axioms_target) $V$ has been defined. Let $\psi, \sigma, \omega \in V$ and $a,b \in \mathbb{F}^1$. 

The vector space $V$ is an algebra over $\mathbb{F}$ if there exists a [binary operation](#binary_operation_glossary), 
\begin{equation}
V \times V \rightarrow V,
\end{equation}
meaning it takes two elements of $V$ as input and maps them to a single element of $V$, that satisfies the following conditions

1. $(\psi + \sigma) \times \omega = \psi \times \omega + \sigma \times \omega$
    - Right distributivity 
2. $\omega \times (\psi + \sigma) = \omega \times \psi + \omega \times \sigma$
    - Left distributivity
3. $(a \psi) \times (b \sigma) = (ab) (\psi \times \sigma)$
    - Compatibility with scalars

The above three conditions can be compactly summarised as saying the binary operator in the definition of the algebra, $\times$, must be bilinear. 

### Examples

::::{tab-set}
:::{tab-item} Cross Product 
:sync: tab1

The vector space of $\mathbb{R}^3$, defined over the field of real numbers $\mathbb{R}$ with bilinear product the [cross product](#cross_product_target_vectors).  

This example can be used to understand the difference between a algebra and an [inner product space](#inner_product_definition_target):

 - $\mathbb{R}^3$ with a cross product $\rightarrow$ algebra
 - $\mathbb{R}^3$ with a [dot product](#dot_product_target_vectors) $\rightarrow$ inner product space

:::
:::{tab-item} Complex Numbers
:sync: tab2

The complex numbers can be defined as a vector space $\mathbb{R}^2$ over the field of real numbers $\mathbb{R}$, such that 
\begin{equation}
x = a + bi \in \mathbb{C}^1
\end{equation}
where $a,b \in \mathbb{R}^1$. The bilinear product is then 
\begin{equation}
(a + bi) \cdot (c + di) = ac + (ad+bc)i - bd,
\end{equation}
which is the product of two complex numbers.  

::::