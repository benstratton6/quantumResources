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
abstract: A short introduction to the concepts in quantum resource theories.
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

```{figure} resourceTheories_introduction_1.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: free_Operatons_allowed_operations_target

a) The free objects of a resource theory inside the set of all objects. A resourceful and a resourceless object are shown b) The set of allowed operations of a resource theory inside the set of all operations.  
```

### Allowed Operations

Allowed operations are resource non-increasing operations. Hence, if there exists an allowed operation $\mathcal{E}$, between two objects $ \rho $ and $ \sigma $, such that $\mathcal{E}(\rho)=\sigma$, then it must be the case that $ \sigma $ has less than or equal to the resource content of $ \rho $. 

The allowed operations define a [preorder](#pre_order_conditions_target) on the space of states [💭](#myDefinitionofPreOrder). If an allowed operation exists mapping a state $\rho$ to $\sigma$ then we write that 
\begin{equation}
    \rho \prec \sigma.
\end{equation}

The preorder determines how resourceful objects are compared to each other and finding it is one of the central goals of any resource theory. 

Allowed operations are typically defined by the physical constraints of the system one is interested in investigating, such as in the resource theory of entanglement. However, they can be mathematically motivated, such as in the resource theory of symmetry.

### Free Objects

Free objects are the set of objects upon which the allowed operations act invariantly. Hence, if an agent - who can only perform allowed operations - has only objects from the free set, they are only able to reach other objects in the free set. 

It is assumed that an agent can generate any arbitrarily large amount of free objects at no cost. If they have an object not in the free set, they can also throw that object away and prepare an object in the free set. Therefore, all elements of the free set are reachable from any other object.  

Objects in the free set are said to be *resourceless*. Any object not in the set of free objects is said to contain *resource*.

## Resource Theory Features
(simulation_of_channels_target)=
### Simulation of Non-allowed Operations 

A resourceful object allows an agent to overcome the physical constraints of their system; if the agent has access to a resourceful object and allowed operations, they will able to perform operations they would not be able to do with allowed operations only. 

Let $\mathcal{P}$ be a non-allowed operation. It could be possible that given some resourceful state $ \rho $, and some allowed operation $\mathcal{E}$, it could be possible to simulate the action of $\mathcal{P}$ on some state $ \psi $, 
\begin{equation}
\mathcal{E}(\psi \otimes \rho) = \mathcal{P}(\psi).
\end{equation}

The most notable example of this would be within the resource theory of entanglement ([](https://link.aps.org/doi/10.1103/RevModPhys.81.865)). Here, the allowed operations are local operations and classical communication ([LOCC](https://en.wikipedia.org/wiki/LOCC)) meaning there is no allow operation that can send quantum information between two spatially separated parties. However, using LOCC (the allow operations) and a shared entangled state between the parties (an state with entanglement is a resource in the resource theory of entanglement) a channel that sends quantum information between the two spatially separated parties can be simulated via the quantum teleportation protocol. 

A central aim of resource theories is to find operations that can be simulated given a particular resourceful object. 

### Operational Interpretations

Once one has defined something to be a resource, how resourceful an object is can be quantified by how well it can perform at some useful task. Typically, this is done by finding different physically meaningful task for which different [resource measures](#quantifying_resource_page_target) limit the agents success in the task. 

For general [convex](#convex_sets_target) resource theories, state discrimination and [state exclusion](#state_exclusion_page_target) have been related to the resource measures of the robustness ([](https://link.aps.org/doi/10.1103/PhysRevX.9.031053)) and weight respectively ([](https://link.aps.org/doi/10.1103/PhysRevLett.125.110402)). 

### Catalysis 

It might be the case that there *does not* exists an allowed operation, $\mathcal{E}$, such that $\sigma = \mathcal{E}(\rho)$ where $ \rho, \sigma $ are not free state. However, there could exists a non-free state, $ \omega $, so that there *does* exists an allowed operation, $\mathcal{E}'$, such that 
\begin{equation}
\mathcal{E}'(\rho \otimes \omega) = \sigma \otimes \omega. 
\end{equation}
The state $ \omega $ is called a catalyst as it facilitates a state change without itself being consumed. 

Within the literature, the above condition for catalyst have been relaxed and studied. For example, the catalyst has been allowed to be returned close but not exactly to its original state or correlations have been allowed to build up between the output state and catalysts such that
\begin{equation}
\mathcal{E}'(\rho \otimes \omega) = \sigma_{SC}, ~ ~ \textrm{where} ~~ \textrm{tr}_{C}( \sigma_{SC}) = \sigma ~ ~ \textrm{and} ~ ~ \textrm{tr}_S(\sigma_{SC}) = \omega,
\end{equation}
where $S$ labels the system and $C$ the catalyst. 

## Further Reading

- [Resource of the Quantum world](https://doi.org/10.48550/arXiv.2402.05474) (Textbook)
- [Quantum Resource Theories](10.1103/RevModPhys.91.025001) (Review Article)
- [Resource theories and their applications in quantum thermodynamics and nonlocality](https://research-information.bris.ac.uk/en/studentTheses/resource-theories-and-their-applications-in-quantum-thermodynamic) (PhD Thesis)
- [Catalysis in Quantum Information Theory](
https://doi.org/10.48550/arXiv.2306.00798
) (Review Article)