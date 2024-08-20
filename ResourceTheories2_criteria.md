---
title: Resource Theories Criteria
subject: 
subtitle: What makes a set of quantum objects a resource theory?
# short_title: How to MyST
authors:
  - name: Benjamin Stratton
    # affiliations:
    #   - Executable Books
    #   - Curvenote
    orcid: 0009-0001-2746-3668
    email: ben.stratton@bristol.ac.uk
license: CC-BY-4.0
keywords: Resource Theories, allowed operations, free states.
abstract: The set of criteria for a set of channels and a set of states to define a static resource theory. The physical interpretations of each criteria is given. 
exports:
  - format: pdf
    template: physical_review_journals
    article_type: Report
--- 

Let $\mathfrak{F}_{AB}$ be a set of quantum channels, mapping from some physical system $A$ to $B$. Let $\mathfrak{O}$ be the set of quantum states for which $\mathfrak{F}_{AB}$ acts invariantly.  

The tuple $\mathcal{R} = (\mathfrak{F}_{AB}, \mathfrak{O})$ is a **quantum resource theory** if:

1. The identity channel, $\mathcal{I}$, is in $\mathfrak{F}_{AB}$, i.e. $\mathcal{I} \in \mathfrak{F}_{AB}$.
    - **Physical interpretation**: If we do nothing we should not expect the state to become resourceful. 

2. If for three physical systems, $A, B, C$ there exists channels such that $\mathcal{E} \in \mathfrak{F}_{AB}$ and $\mathcal{N} \in \mathfrak{F}_{BC}$ then $\mathcal{E} \circ \mathcal{N} \in \mathfrak{F}_{AC}$
    - **Physical Interpretation**: You cannot make something resourceful by applying successive free operations. 

A quantum resource theory $\mathcal{R}$ is said to admit a **tensor product structure if**:

1. The set of allowed operations always includes the $\textrm{tr}(\cdot)$, i.e. $\textrm{tr}(\cdot) \in \mathfrak{F}_{AB}$. 
    - **Physical Interpretation**: This means disregarding physical systems can always be done for free. 

2. For any three physical systems $A,B$ and $C$ and channel $\mathcal{E} \in \mathfrak{F}_{AB}(\cdot)$, the channel $\mathcal{E}_{AB} \otimes \mathcal{I}_{c} \in \mathfrak{F}_{(AC),(BC)}$, where $\mathcal{I}_{C}$ is the identity channel on the space $C$. 
    - **Physical Interpretation**: Free operations are completely free. We cannot turn a free operation into something useful by just embedding the state in some higher dimensional space. 

3. For any state $\sigma \in \mathfrak{O}$, the map $\mathcal{E}(\rho) = \rho \otimes \sigma \in \mathfrak{F}_{AB}$.
    - **Physical Interpretation**: Adding on something that is free is always a free operations. This means that just adding something free cannot make an object more resourceful.  

