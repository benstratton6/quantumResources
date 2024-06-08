---
title: Hilbert Spaces
subject: 
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
keywords: Vector Spaces, Vectors, States.  
abstract: The details of Hilbert spaces, the space in which quantum states are modelled, are given.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Definition 

A Hilbert space is a vector space, $\mathcal{H}$, defined over a field $\mathbb{F}$, with an inner product $(\cdot, \cdot) \rightarrow \mathbb{F}^{1}$ such that the norm defined by 
\begin{equation}
 \vert \vert \bm{x} \vert \vert = \sqrt{(\bm{x}, \bm{x})}
 \end{equation}
turns $\mathcal{H}$ into a complete metric space. Equivalently, a Hilbert space is a inner product space that is complete with respect to the norm $\vert \vert \cdot \vert \vert$ defined above. 

In the following all the concepts needed to understand this definition will be built up. 

## Preliminaries

### Cauchy Sequence 

A **Cauchy sequence** is a sequence whose elements become arbitrarily close as the sequence progresses.   

A sequence of real numbers $\bm{x}_1, \bm{x}_2, \bm{x}_3, \ldots$ is a Cauchy sequence if for every positive real number $ \epsilon $ there exists an $N \in \mathbb{I}^{+}$ and $m,n > N$, such that  
\begin{equation}
\vert \bm{x}_m - \bm{x}_{n} \vert < \epsilon,
\end{equation}
where $\mathbb{N}$ is the set of [natural numbers](https://en.wikipedia.org/wiki/Natural_number) and $\mathbb{I}^{+}$ the positive integers. 

This means that if one picks a distance $ \epsilon $, there will be a point in the sequence where the elements are less then that distance apart. 

### Metric Spaces

A metric space is a set of objects, $M$, and **metric** , $d: M \times M \rightarrow \mathbb{F}$, denoted by the ordered pair $(M,d)$. The metric, or distance function, must satisfies the following conditions for $\bm{x}, \bm{y}, \bm{z}~\in~M$,

1. $d(\bm{x}, \bm{x}) = 0$
    - The distance from a point to itself is zero
2. $d(\bm{x}, \bm{y}) \geq 0$
    - This metric is always positive meaning the distance between two points is always positive. 
3. $d(\bm{x}, \bm{y}) = d(\bm{y}, \bm{x})$
    - The distance from $\bm{x}$ to $\bm{y}$  is the same as the distance from $\bm{x}$ to $\bm{y}$.
4. $d(\bm{x}, \bm{z}) \leq d(\bm{x}, \bm{y}) + d(\bm{y}, \bm{z})$
    - The triangle inequality holds 

#### Cauchy Sequences in Metric Spaces

The notion of Cauchy sequence can be expanded to metric spaces. 

Given a metric space, $(M, d)$, a sequence $\bm{x}_1, \bm{x}_2, \bm{x}_3, \ldots~\in~M$ is Cauchy if for every positive real number $ \epsilon $ there exists an $N \in \mathbb{I}^{+}$ and $m,n > N$, such that
 
\begin{equation}
d(\bm{x}_m, \bm{x}_n) < \epsilon.
\end{equation}

This means that the distance, $d$, between the elements are getting arbitrarily closer together as the sequence progresses. 

### Complete Metric Spaces

A metric space, $(M,d)$, is called complete if every Cauchy sequence of point in $M$ has a limit that is also in $M$. 

### Complete Metric Spaces from an Inner Product Space.

A normed vector space, a vector space $\mathcal{H}$ with a norm $\vert \vert \cdot \vert \vert$, induces a metric (distance function) defined by
\begin{equation}
d(\bm{x}, \bm{y}) \coloneqq \vert \vert \bm{x} - \bm{y} \vert \vert = \vert \vert \bm{y} - \bm{x} \vert \vert,
\end{equation}
where $\bm{x}, \bm{y}~\in~\mathcal{H}$. 

This makes the vector space $\mathcal{H}$ into a metric space $(\mathcal{H}, d)$. 

