---
title: Glossary
subject: 
subtitle: 
# short_title: How to MyST
authors:
  - name: Benjamin Stratton
    # affiliations:
    #   - Executable Books
    #   - Curvenote
    orcid: 
    email:
license: 
keywords:  
abstract: 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

(parity_check_operator_target_glossary)=
**Parity Check**: It can be seen in the second line that one can think of $Z_1 \otimes Z_2$ as measuring the parity of the two physical qubits. If the parity is $0$ then the measurement outcome is $(+1)$; if the parity is $1$ then the measurement outcome is $(-1)$.  

(Code_distance_target_glossary)=
**Code Distance**: This distance of a code is the minimum numbers of errors that will change one codeword to another. Alternatively, the distance of a code is the minimum number of errors that will go undetected. 

(Abelian_group_target_glossary)=
**Abelian Group**: A group in which the result of applying the group operation to two group elements does not depend on the order in which they are written i.e $g_1 \cdot g_2 = g_2 \cdot g_1$. 

(anti_hermitain_pauli_stab_measures_target_glossary)=
**Anti-Hermitian Stabilizers**: If $\tilde{P} \in \mathcal{P}_n$ is not Hermitian, such that $\tilde{P}^\dagger \neq \tilde{P}$, the there exists a $Q \in \mathcal{P}_n$, such that $Q^\dagger = Q$, where $Q=(\pm i) \tilde{P}$. Given the complex phase does not effect the measurement outcomes, one can just measure $Q$ using this method in place of $\tilde{P}$.