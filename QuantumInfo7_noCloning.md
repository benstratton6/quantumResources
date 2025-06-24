---
title: No Cloning Theorem 
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
abstract: Proof that there exists no universal unitary operator that can copy quantum information.
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Copying Classical Information

Given some bit register $\ket{i}$ such that $ i \in \{0,1\}^{\times 1}$, a cloner $C$ is a joint operation on $\ket{i}$ and some empty register, initialised in $\ket{0}$, that copies the information in the first register into the second

\begin{equation}
C (\ket{i} \otimes \ket{0}) = \ket{i} \otimes \ket{i}.
\end{equation}

It can easily be seen that if $C$ is a CNOT gate then the above operation is achievable. 

## Copying Quantum Information

The analogous operation in the quantum case would be some unitary $U_c$ such that 
\begin{equation}
U_c (\ket{\psi} \otimes \ket{0}) = \ket{\psi} \otimes \ket{\psi},
\end{equation}
where $\ket{\psi}$ is some arbitrary quantum state. 

However, it can be shown that no such unitary exists [](https://link.aps.org/doi/10.1103/RevModPhys.77.1225). Below is two proofs of this fact. 

:::{dropdown} Proof 1


The first proof is by linearity. Consider the state 
\begin{equation}
\ket{\Theta} = \frac{1}{\sqrt{2}} \big( \ket{\psi} + \ket{\phi} \big).
\end{equation}

The universal cloner acting on this state should give 
\begin{equation}
U_c (\ket{\Theta} \otimes \ket{0}) = \ket{\Theta} \otimes \ket{\Theta}.
\end{equation}
However, due to linearity it should also give 
\begin{align*}
U_c (\ket{\Theta} \otimes \ket{0}) &= \frac{1}{\sqrt{2}} \big( U_c(\ket{\psi} \otimes \ket{0}) + U_c (\ket{\phi} \otimes \ket{0}) \big) \\
&= \frac{1}{\sqrt{2}} \big( \ket{\psi} \otimes \ket{\psi} + \ket{\phi} \otimes \ket{\phi}) \\
&\neq \ket{\Theta} \otimes \ket{\Theta}.
\end{align*}
The output state is not the desired product state and is instead some entangled state. 
:::

:::{dropdown} Proof 2


The second proof concerns distinguishability. Let $\ket{\psi}$ and $\ket{\phi}$ be two arbitary quantum states such that 
\begin{equation}
0 \leq \vert \braket{\phi | \psi} \vert \leq 1.
\end{equation} 

As we are requiring our cloner to be unitary, it should preserve the inner product. Therefore,
\begin{align*}
( \bra{\psi} \otimes \bra{0} )U^\dagger_c U_c ( \ket{\phi} \otimes \ket{0} ) = ( \bra{\psi} \otimes \bra{0} )( \ket{\phi} \otimes \ket{0} ).
\end{align*}
If one considers the left hand side of the above equation it becomes 
\begin{align*}
( \bra{\psi} \otimes \bra{0} )U^\dagger_c U_c ( \ket{\phi} \otimes \ket{0} ) &= (\bra{\psi} \otimes \bra{\psi})(\ket{\phi} \otimes \ket{\phi}) \\
&= \braket{\psi | \phi}^2.
\end{align*}
The right hand side is then 
\begin{align*}
( \bra{\psi} \otimes \bra{0} )( \ket{\phi} \otimes \ket{0} ) &= \braket{\psi \vert \phi} \braket{0 \vert 0} \\
&= \braket{\psi \vert \phi},
\end{align*}
meaning one has 
\begin{equation}
\braket{\psi | \phi}^2 = \braket{\psi | \phi}.
\end{equation}
This only has a solution if $\braket{\psi | \phi} = 1$, such that $\ket{\psi}=\ket{\phi}$, or $\braket{\psi | \phi}=0$, such that $\ket{\psi}$ is orthogonal to $\ket{\phi}$. This tells us that a universal cloner does exists for states that are othronormal, such as in the example of classical bits above. 
:::

## Broadcasting Quantum Information

The above definition of a cloner was given in terms of pure states but can be generalised to mixed states and subsets of the states as follows: let $\{\rho^i\}_{i}$ be a set of quantum states, then there exists no unitary $U_c$ such that 
\begin{equation}
U_c (\rho^i_A \otimes \vert 0 \rangle \langle  0 \vert_B) U_c = \rho^i_A \otimes \rho^i_B,
\end{equation}
unless all elements of the set $\{\rho^i\}_{i}$ are mutually orthogonal, ${\rm tr}\big[ \rho^j\rho^i \big]= \delta_{ij}~\forall~i,j$. 

This task can be generalised further to the notion of broadcasting, or local cloning, where ones asks if there exists a device such that 
\begin{equation}
(\rho^i_A \otimes \vert 0 \rangle \langle  0 \vert_B) \rightarrow \sigma_{AB},
\end{equation}
where
\begin{equation}
{\rm tr}_{A} \big[\sigma_{AB} \big] = \rho^i, ~ ~ {\rm tr}_{B} \big[\sigma_{AB} \big] = \rho^i.
\end{equation}
It can be shown that broadcasting quantum information is also impossible [](https://link.aps.org/doi/10.1103/PhysRevLett.76.2818).