---
title: Eigenvectors and Eigenvalues
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
keywords: Eigenvectors, eigenvalues, vector spaces, linear maps. 
abstract: A brief overview of eigenvectors and eigenvalues.   
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

Let $V$ be a vector space defined over a field $\mathbb{F}$ and $L: V \rightarrow V$ be a linear map. A vector $\bm{x}~\in~V$, where $\bm{x} \neq 0$, is called an **eigenvector** of the map $L$ if 
\begin{equation}
L(v) = \lambda v,
\end{equation}
where $\lambda~\in~\mathbb{F}^{1}$ is the **eigenvalue** of the eigenvector $v$.

