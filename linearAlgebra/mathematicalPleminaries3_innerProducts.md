---
title: Inner Products 
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
keywords: Vectors, Vector Spaces, Inner Products 
abstract: The conditions for a functional of two vectors to be an inner product. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

A [vector space](#vector_space_axioms_target), $V$, with an inner product is called an *inner product space*. 

An inner product, $(\cdot, \cdot)$, is a functional that takes two vectors from the vector space $V$, defined over a field $\mathbb{F}^{n}$, as an input and outputs a scalar, $(\cdot, \cdot): \mathbb{F}^{n} \otimes \mathbb{F}^{n} \rightarrow \mathbb{F}^{1}$. 

### Inner Product Conditions

Let $\psi, ~\sigma ~\in~V$ and $a \in \mathbb{F}^{1}$.

To be an inner product the functional $(\cdot, \cdot)$ must obeys the following properties:

1. $(\psi, \psi) \geq 0$ and $(\psi, \psi) = 0$ if and only if $\psi=0$
    - Positive-definiteness
2. $(\psi,\omega) = \overline{(\omega, \psi})$
    - Conjugate symmetry
    - If $V$ is defined over $\mathbb{R}$ then $(\psi,\omega) = (\omega, \psi)$
3. $(\psi, a \omega) = a (\psi, \omega)$
    - Linearity in the second argument
    - If $V$ is defined over $\mathbb{C}$ then $(a \psi,\omega) = \overline{a}(\psi, \omega)$
4. $(\psi, \omega + \sigma) = (\psi,\omega) + (\psi, \sigma)$
    - Additivity

