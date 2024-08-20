---
title: Algorithmic Cooling 
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
abstract: The conditions for a protocol to be consider algorithmic cooling  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

Algorithmic Cooling is an information processing protocol that aims to reduce the entropy in some target subsystem, whilst increasing the entropy in the complementary system. This is done by separating a system into a target subsystem to be cooled and a thermal machine to facilitate the cooling. This joint system then interacts with a thermal bath.

[](https://doi.org/10.48550/arXiv.2402.11832) define a unified framework for *coherent control algorithmic cooling*. 

let $\rho_t$ be the target system, $\rho_m$ the thermal machine and $ \tau $ a thermal state from a bath at temperature $T$ such that 
\begin{equation}
\tau = \frac{e^{-\beta H}}{\textrm{tr}[e^{-\beta H}]},~~\beta = \frac{1}{k_b T}.
\end{equation}

Coherent control algorithmic cooling protocols consist of two subroutines: a unitary control step and a thermalisation step.   

1. Unitary Control Step: A unitary, $U_{s,m}$ that acts on both the target and machine subsystems. This step does not need to conserve energy in the system. 
2. Thermalisation Step: a [thermal operation](https://doi.org/10.1038/ncomms3059), $\mathcal{E}$, that acts on the joint target and machine state such that 
\begin{equation}
\mathcal{E}(\rho_{s,m}) = \textrm{tr}_b \big[ V_{s,m,b} \big( \rho_{s,m} \otimes \tau \big) V_{s,m,b}^{\dagger} \big],
\end{equation} 
where $\rho_{s,m}$ is the joint state of the system and thermal machine after a unitary control step and $[V_{s,m,b}, H_{s} + H_m + H_b]=0$. 

A coherent control algorithmic cooling protocol is then defined as a methodical sequence which alternative between a unitary control step and a thermalisation step with the aim to reduce the entropy in the target system. 



