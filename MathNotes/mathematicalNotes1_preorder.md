---
title: Pre Order and Partial Order
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
abstract: The conditions for a pre-order and partial order to exists on a set. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

Let $S$ be some set and $\leq$ be some relation between the elements of the set. 

### Pre-order Conditions

The relation sets a pre-order on the set $S$ if
(pre_order_conditions_target)=
1. $a \leq a$ for all $a~\in~S$
    - Reflexivity
2. $a \leq b$ and $b \leq c$ implies $a \leq c$ where $a,b,c~\in~S$. 
    - Transitivity 

### Partial-order Conditions

The relation sets a partial order on the set $S$ if both 1 and 2 from the pre-order conditions are met and

3. $a \leq b$ and $b \leq a$ implies $a=b$
    - Antisymmetry 