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

```{figure} mathematicalNotes2_convexity_image_1.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: convexity_figure_vectors_target

Two vectors, $p_1$ and $p_2$, drawn with respect to some basis, and the vector that joins them. 
```
The above [figure](convexity_figure_vectors_target) shows two vectors, $p_1$ and $p_2,$ drawn with respect to some basis, and the vector, $p_2 - p_1$ that joins them. Any point along the line that encompasses the vector $p_2 - p_1$ can be given by a vector 
\begin{align*}
\bm{l} &=  t (p_2 - p_1) + p_1 \\
&= (1-t)p_1 + t p_2.
\end{align*}
where $t$ is a scalar. If $t~\in~[0,1]$ that $\bm{l}$ can be considered a probabilistic mixture of the vectors $p_1$ and $p_2$. 

## Convexity Graphically

```{figure} mathematicalNotes2_convexity_image_2.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: convexity_figure_graph_target

A convex function, $f(X)$.  
```
In the above figure, a function $f(X)$ is given. For any two points on the on the graph it can visually be seen that any point on the graph sits below the line-segment between those points. This can be state mathematically as 
\begin{equation}
f(tX_1 + (1-t)X_2) \leq tf(X_1) + (1-t)f(X_2).
\end{equation} 