---
title: Dual Spaces 
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
keywords: Vector Spaces, Vectors, Dual Spaces 
abstract: A brief overview of dual vector spaces  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(dual_vector_spaces_target)=
Given a vector space $V$, the dual space, $V^{*}$, is the space of linear [functionals](#functional_target_glossary) on $V$. Therefore the dual space can be defined as $\Omega : V \longrightarrow \mathbb{F}^{1}$ where $ \Omega $ are funcationals from the vectors in $V$ to scalars $\mathbb{F}^{1}$. $V^{*}$ is itself a [vector space](#vector_space_axioms_target) if it fulfills all the axioms of a vector space, which can do done by adding an addition and scalar multiplication operation. 

Each element in $V$ has a corresponding element in $V^{*}$ that can be thought of as the funcational that takes that element to an element in $\mathbb{F}$. Equally, any [basis](#basis_vector_space_target) in $V$ has a corresponding basis in $V^{*}$.

Dual spaces are often used when working with vectors in non-orthogonal reference frames. Consider a basis $\{e_1, e_2, \ldots, e_{n}\}$ in $V$ and a vector $\bm{a}~\in~V$ with linear decomposition $c_1 e_1 + c_2 e_2 + \ldots c_n e_n$. A basis $\{e^1, e^2, \ldots, e^{n}\}$ can be found in $V^{*}$ such that 
\begin{equation}
e^{i}(c_1 e_1 + c_2 e_2 + \ldots c_n e_n) = c_i.
\end{equation}

