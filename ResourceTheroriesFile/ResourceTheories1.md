---
title: Resource Theories Introduction
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
license: CC-BY-4.0
keywords:  
abstract: A short introduction to the concepts behind resource theories
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

Within a given resource theory, you have objects and resources.

# Allowed Operations

Allowed operations are resource non-increasing by definition. Hence, if there exists an operation $\mathcal{E} \in \mathfrak{F}$ such that $\mathcal{E}(\rho) = \sigma$ where $\rho, \sigma \notin \mathcal{O}$ then it must be the case that $\sigma$ has less than or equal to the resource content of $\rho$. 

The allowed operations define a [preorder](https://en.wikipedia.org/wiki/Preorder) on the space of states [💭](#myDefinitionofPreOrder). If an allowed operation exists mapping a state $\rho$ to $\sigma$ then  
\begin{equation}
    \rho \prec \sigma. 
\end{equation}

**Sources to learn more**

- [Resource of the Quantum world](https://doi.org/10.48550/arXiv.2402.05474) (Textbook)
- [Quantum Resource Theories](10.1103/RevModPhys.91.025001) (Review Article)
- [Resource theories and their applications in quantum thermodynamics and nonlocality](https://research-information.bris.ac.uk/en/studentTheses/resource-theories-and-their-applications-in-quantum-thermodynamic) (PhD Thesis)