---
title: Norms 
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
keywords: Norms, Vector Spaces, Vectors, Matrices 
abstract: The conditions for a [functional](#functional_target_glossary) on a vector space to be a norm and some examples of both vector and matrix norms.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(norms_page_target)=
## Norm Conditions

Let $V$ be a vector space over the field $\mathbb{F}$. A functional, $ \vert \vert \cdot \vert \vert $, on $V$ from it's elements to the positive real numbers, $\vert \vert \cdot \vert \vert: V \rightarrow \mathbb{R}^{+}$ is a norm if it satisfies the following conditions for $\psi, \sigma ~\in ~V$ and $\lambda~\in~\mathbb{F}^{1}$:

1. $\vert \vert \psi \vert \vert \geq 0$ where $\vert \vert \psi \vert \vert=0$ iif $\psi = 0$
    - Positivity 
2. $\vert \vert \lambda \psi \vert \vert = \vert \lambda \vert ~ \vert \vert \psi \vert \vert$
    - Scaling 
3. $\vert \vert \psi + \sigma \vert \vert \leq \vert \vert \psi \vert \vert + \vert \vert \sigma \vert \vert $
    - Triangle Inequality 
    - From this is can be seen that: $\vert ~ \vert \vert \psi \vert \vert - \vert \vert \sigma \vert \vert ~\vert \leq \vert \vert \psi - \sigma \vert \vert$

Norms can be thought of as functionals that measure the size of an elements of a vector space. A vector space with a norm is called a normed vector space. 

## Vector Norm Examples

::::{tab-set}
:::{tab-item} l_p-norm
:sync: tab1
Let $\psi~\in~V$ be a vector such that $\psi~\in~\mathbb{F}^{n}$ with elements $(\psi_1, \psi_2, \ldots, \psi_n)$. The $l_{p}$-norm is given by 
(L2_norm_norms_target)=
\begin{equation}
\vert \vert \psi \vert \vert_{p} = \big( \vert \psi_1 \vert^p + \vert \psi_2 \vert^p + \ldots + \vert \psi_n \vert^p)^{1/p}
\end{equation}
With $p=1$ and $p=2$ being the $1$-norm and Euclidean ($l_2$) Norm:
\begin{align*}
\vert \vert \psi \vert \vert_{1} &= \big( \vert \psi_1 \vert + \vert \psi_2 \vert + \ldots + \vert \psi_n \vert) \\
\vert \vert \psi \vert \vert_{2} &= \big( \vert \psi_1 \vert^2 + \vert \psi_2 \vert^2 + \ldots + \vert \psi_n \vert^2)^{1/2}
\end{align*}
:::
:::{tab-item} Sup-norm
:sync: tab2
Let $\psi~\in~V$ be a vector such that $\psi~\in~\mathbb{F}^{n}$ with elements $(\psi_1, \psi_2, \ldots, \psi_n)$. The Sup-norm is given by 
\begin{equation}
\vert \vert \psi \vert \vert_{\infty} = \max \{\vert \psi_i \vert~: 1 \leq i \leq n \}.
\end{equation}
This is just the maximum elements of $ \psi $. 
:::
::::

## Matrix Norms
In addition to satisfying the above requirements, to be considered a norm on a vector space, $M$, which has matrices as elements, the functional $\Omega: M \rightarrow \mathbb{R}^{+}$ must satisfy the following condition for all $A,B~\in~M$: 

1. $\vert \vert AB \vert \vert \leq \vert \vert A \vert \vert ~ \vert \vert B \vert \vert$

## Matrix Norm Examples

The following norms are all unitarily invariant, meaning $\vert \vert A \vert \vert =  \vert \vert UAU^{\dagger} \vert \vert$. 

::::{tab-set}
:::{tab-item} Trace Norm
:sync: tab3

Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. The trace norm is given by
(trace_norm_target_norms)=
\begin{equation}
\vert \vert A \vert \vert_{\textrm{tr}} = \sum_{i} \mu_{i}(A),
\end{equation}
where $\mu_{i}(A)$ are the singular value of $A$. Hence, the Trace norm of $A$ is the sum of singular values of A. 

It is also given by 
\begin{equation}
\vert \vert A \vert \vert_{\textrm{tr}} = \textrm{tr} \big( \sqrt{A^{\dagger}A} \big). 
\end{equation}


:::
:::{tab-item} Frobenius Norm 
:sync: tab4
Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. The Frobenius norm is given by
(target_Frobenius_Norm_target)=
\begin{equation}
\vert \vert A \vert \vert_{F} = \sqrt{ \sum_{j}^{n} \sum_{i}^{m} \vert a_{ij} \vert ^{2} }.
\end{equation}

It is also given by 
\begin{equation}
\vert \vert A \vert \vert_{F} = \sqrt{\textrm{tr}(A^{\dagger}A)}. 
\end{equation}

:::
:::{tab-item} l_2 norm 
:sync: tab5
Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. Let $\psi~\in~V$ be a vector such that $\psi~\in~\mathbb{F}^{n}$ with elements $(\psi_1, \psi_2, \ldots, \psi_n)$.

The $l_2$ vector norm is given by 
\begin{equation}
\vert \vert \psi \vert \vert_{2} &= \big( \vert \psi_1 \vert^2 + \vert \psi_2 \vert^2 + \ldots + \vert \psi_n \vert^2)^{1/2}
\end{equation}

The $l_2$ norm of a matrix (also called the spectral norm) is given by the induced norm ([operator norm](#operator_norm_target_norms)) of the $l_2$ norm on a vector, 
(ltwo_norm_target_norms)=
\begin{equation}
\vert \vert A \vert \vert_2 = \sup_{\psi} \frac{ \vert \vert A \psi \vert \vert_2 }{ \vert \vert \psi \vert \vert_{2}}
\end{equation}

It is also given by 
\begin{equation}
\vert \vert A \vert \vert_2 = \sqrt{\mu_{\textrm{max}}(A^{\dagger}A)}
\end{equation}

:::
:::{tab-item} Ky Fan Norm
:sync: tab6
Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. The $k$-Ky Fan norm is given by
\begin{equation}
\vert \vert A \vert \vert^{k} _{*} = \sum_{i}^{k} \vert \mu^{\downarrow}_{i}(A) \vert,
\end{equation}
where $\mu^{\downarrow}_i (A)$ is the $i$th singular value of $A$ such that $ \mu^{\downarrow}_i(A) \geq \mu^{\downarrow}_{i+1}(A)~\forall~i$. Hence the Ky Fan Norm is the sum of the $k$th largest singular values.

**Ky Fan Dominance**: Let $B~\in~M$ be a matrix such that $B~\in~\mathbb{F}^{m \times n}$. If it follows that
\begin{equation}
\vert \vert A \vert \vert^{k} _{*} \leq \vert \vert B \vert \vert^{k} _{*},
\end{equation}
for all $k$, then for all unitarily invariant norms it is the case that 
\begin{equation}
\vert \vert A \vert \vert \leq \vert \vert B \vert \vert.
\end{equation}
:::
:::{tab-item} Schatten Norms
:sync: tab7
Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. The Schatten norms are given by
\begin{equation}
\vert \vert A \vert \vert_{p} = \bigg( \sum_{i}^{k} \big[\mu_{i}(A)\big]^{p} \bigg)^{\frac{1}{p}},
\end{equation}
where $\mu_i(A)$ are the singular values of $A$. 

Equally, Schatten norms can be written as 
\begin{equation}
\vert \vert A \vert \vert_{p} = \textrm{tr} \big[ \vert A \vert ^{p} \big]^{\frac{1}{p}},
\end{equation}
where $\vert A \vert = \sqrt{AA^{\dagger}}$. 

If $p=1$ you get the [trace norm](#trace_norm_target_norms), if $p=2$ you get the [Frobenius Norm](#target_Frobenius_Norm_target) and if $p=\infty$ you get the [$l_{2}$ norm](#ltwo_norm_target_norms). 
:::
::::

The following norms are not necessarily unitarily invariant.

::::{tab-set}
:::{tab-item} Operator Norm
:sync: tab8
(operator_norm_target_norms)=
This is an induced norm. 

Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. If $A$ is a linear map such that $A: V \rightarrow W$, where $V$ is a vector space over $\mathbb{F}^{m}$ and $W$ is a vector space over $\mathbb{F}^{n}$ then the operator norm is given by 
\begin{equation}
\vert \vert A \vert \vert_{op} = \inf \{c \geq 0: \vert \vert A \psi \vert \vert_{W} \leq c \vert \vert \psi \vert \vert_{V}~\forall~\psi~\in~V \},
\end{equation}
where $\vert \vert \cdot \vert \vert_{W}$ and $\vert \vert \cdot \vert \vert_{V}$ are vector norms on $V$ and $W$ respectively. 

The operator norm can be colloquially thought of as the maximum amount a map $A$ can lengthen a vector in $V$. 
:::
:::{tab-item} L_pq Norms
:sync: tab9
Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. The $L_{p,q}$ norm, where $p,q \geq 1$, is given by 
\begin{equation}
\vert \vert A \vert \vert_{p,q} = \biggl( \sum^{n}_{j} \bigg( \sum_{i}^{m} \vert a_{ij} \vert^{p} \bigg)^{\frac{q}{p}} \biggl)^{\frac{1}{q}},
\end{equation}
where $a_{ij}$ are the elements of $A$. 

The $L_{2,1}$ norm, which is the sum of the [$l_{2}$ vector norms](#L2_norm_norms_target) of the columns of $A$, is given by 
\begin{equation}
\vert \vert A \vert \vert_{2,1} = \sum^{n}_{j} \vert \vert a_j \vert \vert_{2} = \sum^{n}_{j} \bigg( \sum_{i}^{m} \vert a_{ij} \vert^{2} \bigg)^{\frac{1}{2}}
\end{equation} 
where $a_{j}$ are the columns of the matrix $A$. 
:::
::::


