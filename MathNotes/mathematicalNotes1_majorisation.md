---
title: Majorisation of Vectors
subject: Tutorial
subtitle: 
# short_title: How to MyST
authors:
  - name: Benjamin Stratton
    # affiliations:
    #   - Executable Books
    #   - Curvenote
    orcid: 0009-0001-2746-3668
    email: ben.stratton@bristol.ac.uk
license: 
keywords: Vectors, majorisation. 
abstract: The conditions for one vector to majorisation another and for a function to be Schur-convex.
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

Let $\bm{x}, \bm{y}~\in~\mathbb{R}^{n}$ with components $(x_1, x_2, \ldots, x_n)$ and $(y_1, y_2, \ldots, y_n)$ respectively. 

If $\bm{x}$ majorises $\bm{y}$, then $\bm{y}$ can be considered to be *more mixed* or *closer* to the maximally mixed vector, $I = (1/n, 1/n, \ldots, 1/n)$, then $\bm{x}$. 

$\bm{x}$ majorises $\bm{y}$, typically denoted by $\bm{x} \succ \bm{y}$,
- If and only if, 
\begin{equation}
\sum^{k}_{i} x^{\downarrow}_{i} \geq \sum^{k}_{i} y^{\downarrow}_{i} ~~ \forall ~ k = 1,2, \ldots, n-1 ~ \textrm{with}~ \sum_{i}^{n} x_{i} = \sum_{i}^{n} y_{i}.
\end{equation}
where $x^{\downarrow}_{i}$ and $y^{\downarrow}_{i}$ are the components of $\bm{x}$ and $\bm{y}$ respectively ordered in non-increasing order, such that $x_i \geq x_{i+1}~\forall~i$.

- If and only if there exists a stochastic matrix $A$ satisfying 
\begin{equation}
A \bm{x} = \bm{y}, ~~ A I = I.
\end{equation}

### Schur-convex

A function $f: \mathbb{R}^{n} \rightarrow \mathbb{R}$ is called Schur-convex if and only if 
\begin{equation}
\bm{x} \succ \bm{y} \implies f(\bm{x}) \geq f(\bm{y}).
\end{equation}

A function $f: \mathbb{R}^{n} \rightarrow \mathbb{R}$ is called Schur-concave if and only if 
\begin{equation}
\bm{x} \succ \bm{y} \implies f(\bm{x}) \leq f(\bm{y}).
\end{equation}
