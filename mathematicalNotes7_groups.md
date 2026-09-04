---
title: Groups  
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
keywords: Groups, Group Theory. 
abstract: A brief overview of groups and some important group theory concepts. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

There is much literature on groups, these particular notes were made using [](https://doi.org/10.48550/arXiv.2605.29137).

## Group Definition

Consider a set $G$ and a [binary operation](#binary_operation_glossary) $* :  G \times G \rightarrow G$. Then $(G, *)$ is a group if the following conditions hold: 
(group_page_group_definition)=
1. $(a * b) * c = a * (b * c), ~ ~ a,b,c \in G$
    - Associativity 
2. $ \exists ~ e \in G$ such that $e * g = g * e~\forall~g \in G$
    - Unique identity element
3. $ \forall a \in G, ~ ~\exists~b \in G$ such that $a * b = b * a = e$.
    - Unique inverse element

### Abelian Groups

Let $(G, *)$ be a group. For $a,b \in G$, it is said that $a$ and $b$ commute if $a * b = b*a$. 

A group is said to be abelian if all elements of $G$ mutually commute. If not, it is said to be non-abelian. 

### Subgroups 
(group_page_subgroup_definition)=
Let $(G, *)$ be a group. Given a subset $H \subseteq G$, then $(H, *)$ is a subgroup of $(G, *)$ if $(H, *)$ is [group](#group_page_group_definition). 

### Coset

Let $(G, *)$ be a group and let $(H, *)$ be a [subgroup](#group_page_subgroup_definition) of $(G, *)$. 

For an element $g \in G$:

- The left coset of $(H, *)$ containing $g$ is $gH = \big\{ g*h : h \in H \big\}$
- The right coset of $(H, *)$ containing $g$ is $Hg = \big\{ h*g : h \in H \big\}$

If the group $(G, *)$ is abelian, then the left and right coset are the same. 

Cosets shift a subgroup within the global group.

### Group Examples

::::{tab-set}
:::{tab-item} Integers and addition 
:sync: tab1

Let $\mathbb{Z}$ be the set of all integers. Let $+$ be the binary operation of addition. Then $(\mathbb{Z}, +)$ is a group. 

:::
:::{tab-item} Invertible real and matrix multiplication
:sync: tab2

Let $\mathbb{M}_n$ be the set of $n \times n$ invertible matrices. Let $\times$ be the binary operator of [matrix multiplication](#traget_matrix_multiplication). Then $(\mathbb{M}_n, \times)$ is a group.  

:::
::::


## Group Generators