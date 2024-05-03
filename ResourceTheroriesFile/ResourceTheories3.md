---
title: Quantifying Resources
subject: 
subtitle: How to measure resourcefulness 
# short_title: How to MyST
authors:
  - name: Benjamin Stratton
    # affiliations:
    #   - Executable Books
    #   - Curvenote
    orcid: 0009-0001-2746-3668
    email: ben.stratton@bristol.ac.uk
license: CC-BY-4.0
keywords: Resource Theories, monotones.
abstract: How to quantify how much resource a given object has.  
exports:
  - format: pdf
    template: physical_review_journals
    article_type: Report
--- 

Let $\mathcal{R} = (\mathfrak{F}, \mathfrak{O})$ be a resource theory, where $\mathfrak{F}$ are the allowed operations and $\mathfrak{O}$ are the free states. 


## Resource Measures 
A function $f$ mapping from some state $ \rho $ to a real number, $f: \rho \rightarrow \mathbb{R}$, is a resource measure if 
\begin{equation}
f(\rho) \geq f(\mathcal{E}(\rho))
\end{equation}
where $\mathcal{E} \in \mathfrak{F}$. This means the function is [monotonic](https://en.wikipedia.org/wiki/Monotonic_function) under allowed operations. Physically, this means that the quantifier for $\rho$ cannot be larger for something less resourceful then $\rho$, namely $\mathcal{E}(\rho)$. Resource measures are often just called Monotones.  

## Resource Measures Features
::::{tab-set}
:::{tab-item} Faithfulness
:sync: tab1
A resource measure $f$ is faithful if 
\begin{equation}
f(\rho) = 0 \Longleftrightarrow \rho \in \mathfrak{O}.
\end{equation}
The resource measure is only zero if and only if $ \rho $ is in the free set, i.e. $ \rho $ has no resource. 
:::
:::{tab-item} Convex
:sync: tab2

A resource measure $f$ is convex if
\begin{equation}
f(\rho) \leq pf(\rho_1) + (1-p)f(\rho_2) 
\end{equation}

where $\rho = p\rho_1 + (1-p)\rho_2$ and $0\leq \rho \leq 1$.

This means that taking a mixture of two states does not make it more resourceful. 
:::
::::

***

## Complete Sets of Monotones

Resource measures do not always capture the preorder on the set of states imposed by the allowed operations. It is possible that 
\begin{equation}
f(\rho) \geq f(\sigma)
\end{equation}
even if $\nexists~~\mathcal{E}\in\mathfrak{F}$ such that $\mathcal{E}(\rho) = \sigma$.

A set of resource measures $\{f_{i}\}$ is a complete set of monotones if
\begin{equation}
f_{i}(\rho) \geq f_{i}(\sigma)~\forall~i~~\Longleftrightarrow~ \rho \prec \sigma.
\end{equation}

Complete set of monotones therefore fully capture the preorder on the set of states.

 ## Distance Based Resource Measures

Distance based resource measures are frequently used in Convex resource theories. The aim is to quantify the amount of resource in an object based on its distance from the set of free states. 

A distance measure is a measure that is contractive under quantum channels. A function $d$ from two states to $\mathbb{R}_{\geq 0}$, i.e. $d: \mathcal{H}_{A} \otimes \mathcal{H}_{B} \rightarrow \mathbb{R}_{\geq 0}$, is contractive under a quantum channel $\mathcal{E}$ if 
\begin{equation}
d(\rho, \sigma) \geq d(\mathcal{E}(\rho), \mathcal{E}(\sigma)).
\end{equation}

Resource quantifiers using distances measures usually take the form 
\begin{equation}
f(\rho) = \min_{\sigma \in \mathfrak{O}} d(\rho, \sigma)
\end{equation}