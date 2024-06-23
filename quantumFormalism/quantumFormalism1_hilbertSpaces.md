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
keywords: Vector Spaces, Vectors, Cauchy Sequence, Metric Spaces.  
abstract: The details of Hilbert spaces, the space in which quantum states are modelled, are given.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(hilbert_space_target)=
## Definition 

A Hilbert space is a vector space, $\mathcal{H}$, defined over a field $\mathbb{F}$, with an inner product $(\cdot, \cdot) \rightarrow \mathbb{F}^{1}$ such that the norm induced by the inner product, 
\begin{equation}
 \vert \vert \bm{x} \vert \vert = \sqrt{(\bm{x}, \bm{x})}
 \end{equation}
turns $\mathcal{H}$ into a complete metric space. An equivalently way to phrase this definition is that a Hilbert space is a inner product space that is complete with respect to the norm $\vert \vert \cdot \vert \vert$ defined above. 

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

The definition of a Cauchy sequence is the same for a sequence of vectors, but a norm is considered in place of the absolute value. 

**Properties**

Let $\{ \bm{x}_n \} $ be a Cauchy sequence where $\bm{x} \in \mathbb{R}$ or $\mathbb{C}$. The following properties hold:

1. There exists an $L \in \mathbb{N}$ such that $\vert \bm{x}_m \vert \leq L$ for all $n$
    - Every Cauchy sequence is bounded, this means there exists some number for which the absolute value of all elements of the sequence are upper-bounded by. 
2. Every Convergent sequence is Cauchy. 
    - A sequence is convergent if there exists a $\bm{x}$ such that $\lim_{n \rightarrow \infty} \bm{x}_n = \bm{x}$.
3. Every real or complex Cauchy sequence is convergent. 
    - This means that in the limit of $n \rightarrow \infty $ of all Cauchy sequences they will tend to a fixed value.  

### Metric Spaces

A metric space is a set of objects, $M$, and **metric** , $d: M \times M \rightarrow \mathbb{F}$, denoted by the ordered pair $(M,d)$. The metric, or distance function, must satisfies the following conditions for $\bm{x}, \bm{y}, \bm{z}~\in~M$,

1. $d(\bm{x}, \bm{x}) = 0$
    - The distance from a point to itself is zero
2. $d(\bm{x}, \bm{y}) \geq 0$
    - This metric is always positive meaning the distance between two points is always positive. 
3. $d(\bm{x}, \bm{y}) = d(\bm{y}, \bm{x})$
    - The distance from $\bm{x}$ to $\bm{y}$  is the same as the distance from $\bm{y}$ to $\bm{x}$.
4. $d(\bm{x}, \bm{z}) \leq d(\bm{x}, \bm{y}) + d(\bm{y}, \bm{z})$
    - The triangle inequality holds 

#### Cauchy Sequences in Metric Spaces

The notion of a Cauchy sequence can be expanded to metric spaces. 

Given a metric space, $(M, d)$, a sequence $\bm{x}_1, \bm{x}_2, \bm{x}_3, \ldots~\in~M$ is Cauchy if for every positive real number $ \epsilon $ there exists an $N \in \mathbb{I}^{+}$ and $m,n > N$, such that
 
\begin{equation}
d(\bm{x}_m, \bm{x}_n) < \epsilon.
\end{equation}

This means that if one picks a distance $ \epsilon $, there will be a point in the sequence where the distance between the elements, as given by the function $d$, are less then $ \epsilon $ apart. Hence, the distance, $d$, between the elements are getting arbitrarily closer together as the sequence progresses. 

#### Complete Metric Spaces

A metric space, $(M,d)$, is called complete if every Cauchy sequence of points in $M$ has a limit that is also in $M$. 

Hence, a metric space is incomplete if there exists Cauchy sequences of points in $M$ for which the limit is not in $M$. The significance of this is that there are 'holes' in the space $M$. A Cauchy sequence is a list of elements $\bm{x}_1, \bm{x}_2, \ldots~\in~M$ that are getting arbitrary closer to each other as the sequence progresses. This can be thought of as the distance between the elements getting smaller. In the limit, the elements will tend to some point $\bm{x}$. One could therefore consider the sequence to be an ever finer degree of coarse graining of the space leading up to the point $\bm{x}$. If the convergence point of the sequence, $\bm{x}$, (the limit of the coarse graining) is not in the space $M$, this can be seen as 'hole' in the sense that all the points around it, up to an arbitrary small distance, are in $M$ but the point itself is not in $M$. 

### Branch Spaces: Metric Spaces from an Inner Product Space.

A normed vector space, a vector space $\mathcal{H}$ with a norm $\vert \vert \cdot \vert \vert$, induces a metric (distance function) defined by
\begin{equation}
d(\bm{x}, \bm{y}) \coloneqq \vert \vert \bm{x} - \bm{y} \vert \vert = \vert \vert \bm{y} - \bm{x} \vert \vert,
\end{equation}
where $\bm{x}, \bm{y}~\in~\mathcal{H}$. 

This makes the vector space $\mathcal{H}$ into a metric space $(\mathcal{H}, d)$. A space $\mathcal{H}$ is called a [Branch space](https://en.wikipedia.org/wiki/Banach_space) if the metric space $(\mathcal{H}, d)$ is complete.

A Hilbert space is a Branch space with respect to the norm defined by 
\begin{equation}
 \vert \vert \bm{x} \vert \vert = \sqrt{(\bm{x}, \bm{x})}
 \end{equation}
where $(\cdot, \cdot)$ is the inner product. 

In summary, a Hilbert space is a vector space with an inner product, such that the norm induced by the inner product can be used to define a complete metric space. This then means that the vector space has no 'holes'.

 

