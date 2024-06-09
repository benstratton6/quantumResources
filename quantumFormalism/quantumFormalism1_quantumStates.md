---
title: Quantum States
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
keywords: States, Vectors, Hilbert Spaces, Density Operators.  
abstract: The details of how quantum states are modelled.    
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Definition 

A quantum state is modelled as a Vector in a Hilbert space. 

## Notation

In [Dirac notation](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation), A quantum state is denoted via a ket,
\begin{equation}
\ket{\psi} ~ \in ~\mathcal{H},
\end{equation}
where $ \psi $ is just some label and $\mathcal{H}$ is a Hilbert space. 

This is a universal way to represent quantum states that is independent of the underlying Hilbert space upon which it is defined e.g. if the Hilbert is finite or infinite dimensional. In addition, it is a basis independent was to represent the quantum state. 

## States as Column Vectors 

The smallest quantum systems are states of dimension $2$, known as qubits (quantum bits). They are model by vectors in a Hilbert space defined over $\mathbb{C}^{2}$, where $\mathbb{C}$ are the complex numbers. Hence, one can write the state of a qubit $\ket{\psi}$ as 
\begin{equation}
\ket{\psi} = \begin{pmatrix} \alpha \\ \beta \end{pmatrix} ~ \in ~ \mathcal{H}^{2},
\end{equation}
where $\alpha, \beta~\in~\mathbb{C}$. 

Note, when writing a column vector, one must do so with respect to a given [basis](#basis_page_target), meaning the column vector of a quantum state is not unique. Vectors of a basis can also be written as kets. For example, the [standard basis](#standard_basis_basis_target) in $2$ dimensions denoted in terms of kets is 
\begin{equation}
\ket{0} = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, ~ ~ ~ \ket{1} = \begin{pmatrix} 0 \\ 1 \end{pmatrix}.
\end{equation}
The state $ \ket{\psi} $ written with respect to the standard basis is then
\begin{align*}
\ket{\psi} &= \alpha \begin{pmatrix} 1 \\ 0 \end{pmatrix} + \beta \begin{pmatrix} 0 \\ 1 \end{pmatrix} \\
&= \alpha \ket{0} + \beta \ket{1}.
\end{align*}

General quantum states of finite dimensional $d$ are then modelled as vectors in a Hilbert space defined over $\mathbb{C}^{d}$. If the standard basis is given by the set of vectors $\{ \ket{i} \}_{i=0}^{d-1}$ then any state in the space, $ \ket{\psi} $ can be decomposed into this basis as 
\begin{equation}
\ket{\psi} = \sum_{i} \psi_i \ket{i},
\end{equation}
where $\psi_i$ are coefficients.     