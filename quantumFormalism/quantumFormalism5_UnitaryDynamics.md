---
title: Evolution
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
keywords: Unitaries, Dynamics, Evolution.  
abstract: The details of how quantum states evolve.    
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

The time evolution of a closed quantum system (one not interacting with the environment and hence described by a ket vector) is given by the Schrödinger equation, 
\begin{equation}
i \hbar \frac{d}{dt} \ket{\psi} = H \ket{\psi},
\end{equation}
where $H$ is a hermitian  operators called the [Hamiltonian](#https://en.wikipedia.org/wiki/Hamiltonian_(quantum_mechanics)). The Hamiltonian describes the energy landscape the system exists within and hence is dependent on the system being modelled. 

If a state $\ket{psi}$ is evolved into a state $\ket{\psi'}$ from $t_1$ to $t_2$, the solution to the Schrödinger equation is  
\begin{equation}
\ket{\psi'} = \exp \bigg[ \frac{-iH(t_1 - t_2)}{\hbar} \bigg] \ket{\psi}. 
\end{equation}

This is a [unitary operator](#target_unitary_adjoint_page), meaning that the time evolution of a closed quantum system is given by the action of a unitary operator on the current state. 

:::{dropdown} Proof

The following facts will be used 

1. The exponential of an operator $X$ is given by 
\begin{equation}
e^{X} = \sum_{k=0}^{\infty} \frac{X^k}{k!} = \mathbb{I} + X + \frac{X^2}{2} + \frac{X^3}{6} + \ldots
\end{equation}

from this one gets 

2. $e^{A}e^{B}=e^{A+B}$ if $[A,B] = 0$ 
3. $(e^{A})^{\dagger} = e^{A^{\dagger}}$ as $(A^{n})^{\dagger} = (AA \ldots A)^{\dagger} = (A^{\dagger})^{n}$

Let
\begin{equation}
U = e^{A}
\end{equation}
where
\begin{equation}
A = \frac{-iH(t_1 - t_2)}{\hbar}.
\end{equation}
Hence,  
\begin{align*}
A^{\dagger} &= \bigg[ \frac{-iH(t_1 - t_2)}{\hbar} \bigg]^{\dagger} \\
&= \frac{iH^{\dagger}(t_1 - t_2)}{\hbar} \\
&= \frac{iH(t_1 - t_2)}{\hbar} \\
&= -A,
\end{align*}
where the fact that $H=H^{\dagger}$ has been used. This means that 
\begin{align*}
U^{\dagger} &= \big[ e^{A} \big]^{\dagger} \\
&= e^{A^{\dagger}} \\
&= e^{-A}.
\end{align*}
Hence, 
\begin{align*}
UU^{\dagger} &= e^{A}e^{-A}, \\
&= e^{A-A} \\
&= e^{0},
\end{align*}
where $0$ is the zero operator. The operator expansion of the exponential of the zero operator then gives the identity, 
\begin{equation}
e^{0} = \mathbb{I}.
\end{equation}
Repeating for $U^{\dagger}U$ completes the proof. 
:::

One can therefore succinctly model evolution in quantum theory through unitary operators, 
\begin{equation}
\ket{\psi'} = U \ket{\psi}, ~ ~ UU^{\dagger} = U^{\dagger}U = \mathbb{I},
\end{equation} 
without concern for what the specific Hamiltonian is. 