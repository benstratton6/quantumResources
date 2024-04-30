---
title: Convexity 
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
keywords:  
abstract: The conditions for a set to be convex. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Lines Between Points

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

## Convex Functions

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

## Convex Sets