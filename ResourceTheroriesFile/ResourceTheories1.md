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
abstract: A short introduction to the concepts in quantum resource theories
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Introduction 

Quantum resource theories quantify the usefulness of certain quantum phenomena in information process protocols ([](10.1103/RevModPhys.91.025001)). They provide a rigorous mathematical framework with which to compare the ability of quantum objects to provide an advantage in information processing tasks, subject to certain physical constraints. By tailoring these constraints, quantum resource theories can be applicable to tasks of both a pragmatic and fundamental nature. Thus far they have proved a fruitful way to approach problems concerning a number of different quantum phenomena, with resource theories of entanglement ([](10.1103/RevModPhys.81.865)), athermality ([](10.1088/1751-8113/49/14/143001), [](10.1038/ncomms3059), [](10.1016/j.physrep.2015.04.003), [](10.1088/1361-6633/ab46e5)), Bell-non locality ([](10.1103/RevModPhys.86.419)), measurement ([](10.1103/physrevlett.122.140403)),  and non-Gaussianity ([](10.1103/RevModPhys.84.621)) to name a few. 

## Framework

### Overview

Value emerges from limitation. The study of these limitations, that arise from some set of physical constraints, is the central goal of resource theories. Within these theories, some agent is allowed to perform some operations, whilst other operations are prohibited by the physical constraints. This restricts what it is possible for an agent to generate within the framework, with anything the agent is unable to generate considered a resource. The agents inability to access these resources arbitrarily then ascribes them value. These resource can then be utilised for a variety of tasks that would not be possible solely using allowed operations.  

Within a given resource theory, one therefore has allowed operations and free objects.

### Allowed Operations

Allowed operations are resource non-increasing operations. Hence, if there exists an allowed operation $\mathcal{E}$, between two objects $\rho$ and $\sigma$, such that $\mathcal{E}(\rho)=\sigma$, then it must be the case that $\sigma$ has less than or equal to the resource content of $\rho$. 

The allowed operations define a [preorder](#pre_order_conditions_target) on the space of states [💭](#myDefinitionofPreOrder). If an allowed operation exists mapping a state $\rho$ to $\sigma$ then we write that 
\begin{equation}
    \rho \prec \sigma.
\end{equation}

Allowed operations are defined by the physical constraints of the system one is interested in investigating

### Free Objects


### Operational Interpretations

Once one has defined something to be a resource, how resourceful an object is can be quantified by how well it can perform at some useful task. 

**Sources to learn more**

- [Resource of the Quantum world](https://doi.org/10.48550/arXiv.2402.05474) (Textbook)
- [Quantum Resource Theories](10.1103/RevModPhys.91.025001) (Review Article)
- [Resource theories and their applications in quantum thermodynamics and nonlocality](https://research-information.bris.ac.uk/en/studentTheses/resource-theories-and-their-applications-in-quantum-thermodynamic) (PhD Thesis)