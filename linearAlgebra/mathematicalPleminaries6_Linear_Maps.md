---
title: Linear Maps 
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
keywords: Linear Maps, Matrices, Vector Spaces 
abstract: A brief overview of maps, the conditions for a map to be a linear maps and some of there properties. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

A map from a vector space $V$ to a vector space $V'$ is a rule which assigns to every element of $V$ an elements in $V'$. 

- A map from a space defined over $\mathbb{F}^{1}$ to $\mathbb{F}^{1}$ is called a function.
- A map from a space defined over $\mathbb{F}^{n}$ to $\mathbb{F}^{1}$ is called a [functional](#functional_target_glossary).
- A map from a space defined over $\mathbb{F}^{n}$ to $\mathbb{F}^{m}$ is called an operator. 

A map $L: \mathbb{F}^{n} \rightarrow \mathbb{F}^{m}$ is called a **linear map** if
- $L(\bm{x} + \bm{y}) = L(\bm{x}) + L(\bm{y})$ forall $\bm{x}, \bm{y} \in \mathbb{F}^{n}$. 
- $L(\lambda \bm{x}) = \lambda L(\bm{x})$ where $\lambda ~ \in ~ \mathbb{F}^{1}$