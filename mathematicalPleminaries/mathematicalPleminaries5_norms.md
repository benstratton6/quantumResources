---
title: Vector and Matrix Norms 
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
keywords: Vector Spaces, Vectors, Matrices, Norms 
abstract: The conditions for a function to be a norm  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Norm Conditions

Let $V$ be a vector space over the field $\mathbb{F}$. A functional, $ \Omega $, on $V$ from it's elements to the positive real numbers, $\Omega: V \rightarrow \mathbb{R}^{+}$ is a norm if it satisfies the following conditions for $\psi, \sigma, \omega ~\in ~V$ and $\lambda~\in~\mathbb{F}^{1}$:

1. $\Omega(\psi) \geq 0$ where $\Omega(\psi)=0$ iif $\psi = 0$
    - Positivity 
2. $\vert \vert \lambda \psi \vert \vert = \vert \lambda \vert ~ \vert \vert \psi \vert \vert$
    - Scaling 
3. $\vert \vert \psi + \sigma \vert \vert \leq \vert \vert \psi \vert \vert + \vert \vert \sigma \vert \vert $
    - Triangle Inequality 
    - From this is can be seen that: $\vert ~ \vert \vert \psi \vert \vert - \vert \vert \sigma \vert \vert ~\vert \leq \vert \vert \psi - \sigma \vert \vert$

## Vector Norm Examples

::::{tab-set}
:::{tab-item} L_p-norm
:sync: tab1
Let $\psi~\in~V$ be a vector such that $\psi~\in~\mathbb{F}^{n}$ with elements $(\psi_1, \psi_2, \ldots, \psi_n)$. The $l_{p}$-norm is given by 
\begin{equation}
\vert \vert \psi \vert \vert_{p} = \big( \vert \psi_1 \vert^p + \vert \psi_2 \vert^p + \ldots + \vert \psi_n \vert^p)^{1/p}
\end{equation}
With $p=1$ and $p=2$ being the $1$-norm and Euclidean Norm:
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
This is just the maximum elements of $\psi$. 
:::
::::

## Matrix Norms
In addition to satisfying the above requirements, to be considered a norm on a vector space which has matrices as elements, $M$, the functional $\Omega: M \rightarrow \mathbb{R}^{+}$ must satisfy the following condition for all $A,B~\in~M$: 

1. $\vert \vert AB \vert \vert \leq \vert \vert A \vert \vert ~ \vert \vert B \vert \vert$

## Matrix Norm Examples

::::{tab-set}
:::{tab-item} 
:sync: tab3

:::
:::{tab-item} Ky Fan Norm
:sync: tab4
Let $A~\in~M$ be a matrix such that $A~\in~\mathbb{F}^{m \times n}$. The $k$-Ky Fan norm is given by
\begin{equation}
\vert \vert A \vert \vert _{*} = \sum_{i}^{k} \vert \mu_{i}(A) \vert,
\end{equation}
where $\mu_i (A)$ is the $i$th singular value of $A$ such that $ \mu_i(A) \geq \mu_{i+1}(A)~\forall~i$. Hence the Ky Fan Norm is the sum of the $k$th largest singular values.
:::
::::