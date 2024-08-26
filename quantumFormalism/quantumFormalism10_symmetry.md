---
title: Symmetry 
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
keywords: Symmetry, Conservations Laws, Expectation Values, Noethers Theorem 
abstract: Symmetry in quantum mechanics and how it leads to conservation laws. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Definition 

### Operator 

An operator $A$ is symmetric with respect to the transformation $U$ if 
\begin{equation}
U^\dagger A U = A \Longleftrightarrow [A,U] = 0.
\end{equation}

If $A$ is an observable, this means neither the expectation value, or the probabilities of getting the different possible measurement outcomes of $A$, does not change if the state is evolved by $U$. 

:::{dropdown} Proof
:open:

Let $\ket{\psi} \in \mathcal{H}$, $\ket{\psi'} = U \ket{\psi}$ where $U$ is a unitary, and $A$ be an observable acting on $\mathcal{H}$.

$A$ is symmetric under $U$, meaning that $[A,U] = 0$. 

Consider the expectation value of $A$ with respect to the state $\ket{\psi'}$,

\begin{align*}
\braket{A}_{\psi'} &= \bra{\psi'} A \ket{\psi'}, \\
&= \bra{\psi} U^\dagger A U \ket{\psi}, \\
&= \bra{\psi} U  \ket{\psi}, \\
&= \braket{A}_{\psi}
\end{align*}

hence, the expectation value of $A$ does not change if a state is evolved via $U$. 


:::

### States 

A state $\ket{\psi}$ is symmetric with respect to the transformation $U$ if 
\begin{equation}
U \ket{\psi} = e^{i \theta} \ket{\psi},
\end{equation}
for some $\theta$. 

As global phases cannot be measured, this means that the state $\ket{\psi}$ is unchanged in any measurable way by the transformation $U$. 
