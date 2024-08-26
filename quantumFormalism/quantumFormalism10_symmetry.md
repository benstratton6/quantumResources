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

## Operators

An operator $A$ is symmetric with respect to the transformation $U$ if 
\begin{equation}
U^\dagger A U = A \Longleftrightarrow [A,U] = 0.
\end{equation}

If $A$ is an observable, this means neither the expectation value nor the probabilities of getting the different possible measurement outcomes of $A$ change if the state is evolved by $U$. 

:::{dropdown} Proof


Let $\ket{\psi} \in \mathcal{H}$, $\ket{\psi'} = U \ket{\psi}$ where $U$ is a unitary, and $A$ be an observable acting on $\mathcal{H}$.

Assume $A$ is symmetric under $U$, meaning that $[A,U] = 0$. 

Consider the expectation value of $A$ with respect to the state $\ket{\psi'}$,

\begin{align*}
\braket{A}_{\psi'} &= \bra{\psi'} A \ket{\psi'}, \\
&= \bra{\psi} U^\dagger A U \ket{\psi}, \\
&= \bra{\psi} A  \ket{\psi}, \\
&= \braket{A}_{\psi},
\end{align*}

meaning the expectation value of $A$ does not change if a state is evolved via $U$. 

Now, consider the spectral decomposition of $A$, 
\begin{equation}
A = \sum_n \lambda_n P_n.
\end{equation}
The condition $U^\dagger A U = A$ then becomes 
\begin{equation}
\sum_n \lambda_n U^\dagger P_n U = \sum_n \lambda_n P_n,
\end{equation}
using linearity. Note that $U^\dagger P_n U$ is still a projector for all $n$, 
\begin{equation}
\big( U^\dagger P_n U \big)^2 = U^\dagger P_n U U^\dagger P_n U = U^\dagger P_n U,
\end{equation}
and each $U^\dagger P_n U$ are orthogonal for different $n$,
\begin{equation}
\textrm{tr} \big[ U^\dagger P_n U U^\dagger P_m U \big] = \textrm{tr} \big[ P_n P_m \big] = \delta_{nm},
\end{equation}
this is because they are the projectors onto the eigenspace of $U^\dagger A U$. In order for the equality to hold (with each $\lambda_n$ be associated to a unique subspace) is for $\Pi_n = U^\dagger \Pi_n U$. The probability of measuring the observable $A$ on the state $\ket{\psi'}$ and getting the outcomes $\lambda_n$ is then 
\begin{align*}
P(\lambda_n \vert A) &= \bra{\psi'} P_n \ket{\psi'}, \\
&= \bra{\psi} U^\dagger P_n U \ket{\psi}, \\
&= \bra{\psi} P_n \ket{\psi}, 
\end{align*}
which is the same probability of measuring the observable $A$ on the state $\ket{\psi}$ and getting the outcome $\lambda_n$. 

:::

### Symmetry in Continuous Transformations

Continuous transformations are parameterised by real numbers which dictate the amount of transformation taking place. Such transformations include those in time, space, or rotations.  

Transformations of this type are represented by the exponent of a generator operator, which is an observable. This is captured by [Stone's theorem](https://en.wikipedia.org/wiki/Stone's_theorem_on_one-parameter_unitary_groups). 

The most common continuous transformations considered and the Hermitian operators (observables) that generate them are

::::{tab-set}
:::{tab-item} Time
:sync: tab1

**Unitary:** $U(t) = e^{-\frac{i}{\hbar}~H~t}$

**Generator:** $H$ - Hamiltonian

**Parameter:** $t$ - time

:::
:::{tab-item} Space
:sync: tab2

**Unitary:** $U(a) = e^{-\frac{i}{\hbar}~P~a}$

**Generator:** $P$ - Momentum 

**Parameter:** $a$ - displacement


:::
:::{tab-item} Rotation 
:sync: tab3

**Unitary:** $U(\theta) = e^{-\frac{i}{\hbar}~L_\alpha~\theta}$

**Generator:** $L_\alpha$ - Angular Momentum in $\alpha \in \{x,y,z\}$ 

**Parameter:** $\theta$ - angle (mod $2\pi$)

::::

For an observable, $A$, to be symmetric with respect to the continuous transformation, generator by the observable $G$, it must be the case that 
\begin{equation}
[ U(q) , A ] = 0, ~ ~ ~  U(q) = e^{-\frac{i}{\hbar}~G~q},
\end{equation}
which is possible if and only if $[G,A] = 0$. 

### Conservation Laws

## States 

A state $\ket{\psi}$ is symmetric with respect to the transformation $U$ if 
\begin{equation}
U \ket{\psi} = e^{i \theta} \ket{\psi},
\end{equation}
for some $\theta$. As global phases cannot be measured, this means that the state $\ket{\psi}$ is unchanged in any measurable way by the transformation $U$. 
