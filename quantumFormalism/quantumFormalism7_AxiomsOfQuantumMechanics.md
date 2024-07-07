---
title: Axioms Of Quantum Mechanics
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
keywords: Axioms, states, evolution, measurement, state vectors, density operators. 
abstract: The axioms of quantum mechanics for closed quantum systems both in terms of state vectors and density operators. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

### In terms of State Vectors 

1. **States** - The state of any physical systems is represented by normalised vector in a complex Hilbert space, $ \ket{\psi}~\in~\mathcal{H}$, where $\braket{\psi|\psi} = 1$.

2. **Evolution** - closed quantum systems evolve via unitary operators
\begin{equation}
\ket{\psi'} = U \ket{\psi} U^{\dagger}, ~ ~ \textrm{where} ~ ~ UU^{\dagger} = U^{\dagger}U = \mathbb{I}.
\end{equation}

3. **Measurement** - Observables are given by Hermitian operators. For the observable $O = \sum \lambda_k \ket{\lambda_k}\bra{\lambda_k}$: 
    - The probability of measuring $O$ and getting the outcome $ \lambda_k $ is 
    \begin{equation}
    \textrm{Prob}(\lambda_k) = \vert \braket{\lambda_k|\psi} \vert^{2}
    \end{equation}
    - The expectation value of $O$ is given by 
    \begin{equation}
    \braket{O} = \bra{\psi} O \ket{\psi} = \sum_k \lambda_k \vert \braket{\lambda_k|\psi} \vert^{2}
    \end{equation}
    - The state after measuring $O$ and getting the measurement outcome $ \lambda_k $ is given by 
    \begin{equation}
    \rho_{post} = \frac{ \ket{\lambda_k}\bra{\lambda_k} \rho \ket{\lambda_k}\bra{\lambda_k} }{\vert \braket{\lambda_k|\psi} \vert^{2}}
    \end{equation}

### In terms of density operators

1. **States** - The state of any physical systems is represented by a density operator $ \rho $, where $ \rho \geq 0, ~ \textrm{tr} \big[ \rho \big] = 1$.

2. **Evolution** - closed quantum systems evolve via unitary operators
\begin{equation}
\rho' = U \rho U^{\dagger}, ~ ~ \textrm{where} ~ ~ UU^{\dagger} = U^{\dagger}U = \mathbb{I}.
\end{equation}

3. **Measurement** - Observables are given by Hermitian operators. For the observable $O = \sum \lambda_k \ket{\lambda_k}\bra{\lambda_k}$: 
    - The probability of measuring $O$ and getting the outcome $ \lambda_k $ is 
    \begin{equation}
    \textrm{Prob}(\lambda_k) = \textrm{tr}\big[ \rho \ket{\lambda_k}\bra{\lambda_k} \big]
    \end{equation}
    - The expectation value of $O$ is given by 
    \begin{equation}
    \braket{O} = \textrm{tr} \big[ \rho O \big]
    \end{equation}
    - The state after measuring $O$ and getting the measurement outcome $ \lambda_k $ is given by 
    \begin{equation}
    \rho_{post} = \frac{ \ket{\lambda_k}\bra{\lambda_k} \rho \ket{\lambda_k}\bra{\lambda_k} }{\textrm{tr}\big[ \rho \ket{\lambda_k}\bra{\lambda_k} \big]}
    \end{equation}