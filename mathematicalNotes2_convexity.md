---
title: Convex and Affine Sets
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
keywords: Sets, Convex, Affine.
abstract: The conditions for a set to be convex and affine. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

### Lines Between Points

```{figure} mathematicalNotes2_convexity_image_1.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: convexity_figure_vectors_target

Two vectors, $p_1$ and $p_2$, drawn with respect to some basis, and the vector that joins them. 
```
The above [figure](convexity_figure_vectors_target) shows two vectors, $p_1$ and $p_2,$ drawn with respect to some basis, and the vector, $p_2 - p_1$, that joins them. Any point along the line that encompasses the vector $p_2 - p_1$ can be given by a vector 
\begin{align*}
\bm{l} &=  t (p_2 - p_1) + p_1 \\
&= (1-t)p_1 + t p_2.
\end{align*}
where $t$ is a scalar. If $t~\in~[0,1]$ then $\bm{l}$ can be considered to be a probabilistic mixture of the vectors $p_1$ and $p_2$. 

### Convex Functions

```{figure} mathematicalNotes2_convexity_image_2.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: convexity_figure_graph_target

A convex function, $f(X)$.  
```
In the above figure, a function $f(X)$ is plotted. For any two points on the graph, $x_1$ and $x_2$, it can be seen that the value $f(x')$ is less then $f(x_1)$ and $f(x_2)$ if $x_1 \leq x' \leq x_2$. This means all points between $x_1$ and $x_2$ sit below the line-segment between those points. This can be stated mathematically as 
\begin{equation}
f(tx_1 + (1-t)x_2) \leq tf(x_1) + (1-t)f(x_2).
\end{equation} 
The argument of the left hand side, $tx_1 + (1-t)x_2$, is the straight line between $x_1$ and $x_2$. The right hand side is the straight line between $f(x_1)$ and $f(x_2)$.

If the above criteria is satisfied, the function $f(X)$ is a convex function. 

(convex_sets_target)=
### Convex Sets

```{figure} mathematicalNotes2_convexity_image_3.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: convexity_figure_sets_target

a) A convex set b) a non-convex set.  
```

Let $V$ be a vector space over a field $\mathbb{F}$. A subset $S \subset V$ is convex if for all $\psi, \sigma~\in~S$ the line segment connecting $ \psi $ and $ \sigma $ is also in $S$, as seen in Fig (a) above. Mathematically this means that 
\begin{equation}
t\psi + (1-t) \sigma~\in~S,~\forall~(\psi,\sigma)\in S,~~ t\in[0,1].
\end{equation}
If a mixture of elements in the subset can lead to an element outside of the subset, as seen in fig (b) above where some points on the line segment are outside the boundary of the set, the subset is not convex. 

In general, a set $S$ is convex if for all subsets of objects in $S$,  $\{ \psi_1, \psi_2, \ldots, \psi_n \} \in S~\forall~\psi_i$, then 
\begin{equation}
a_1 \psi_1 + a_2 \psi_2 + \ldots + a_n \psi_n~\in~S,~~ a_i \geq 0 ~\forall~i, ~ ~ \sum_{i=1}^{n} a_i = 1.
\end{equation}

The boundary of a convex set is always a convex curve.

The convex hull of a set $S' \subset V$ is the smallest convex set that contains $S'$. 

### Affine 

Let $V$ be a vector space over a field $\mathbb{F}$. A subset $S \subset V$ is affine if for every pair in the set the whole infinite line through those two points is in $S$. Mathematically, this means that 
\begin{equation}
t \psi + (1-t) \sigma ~\in~S, ~\forall~(\psi, \sigma)\in S. 
\end{equation} 
The key difference between affine sets and convex sets is that $t$ does not need to be in the set $[0,1]$ and can be negative. This means that the *whole line* including $ \psi $ and $ \sigma $ is included, not just the line segment *between* $ \psi $ and $ \sigma $. 

In general, a set $S$ is affine if for all subsets of objects in $S$,  $\{ \psi_1, \psi_2, \ldots, \psi_n \} \in S~\forall~\psi_i$, then 
\begin{equation}
a_1 \psi_1 + a_2 \psi_2 + \ldots + a_n \psi_n~\in~S, ~ \sum_{i=1}^{n} a_i = 1.
\end{equation}
where, as before, the condition for $a_i$ to be positive has been removed. 

Hence, convex combinations can be thought of as a weighted average of elements of the set, whilst affine combinations can be thought of as a weighted average where the weights can be negative. 