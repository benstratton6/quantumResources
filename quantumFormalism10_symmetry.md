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
(symmetric_operator_definition_target_symmetryPage)=
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
(continuous_transformations_target)=
Continuous transformations are parameterised by real numbers which dictate the amount of transformation taking place. Such transformations include those in time, space, or rotations.  

Transformations of this type are represented by the exponent of a generator operator, which is an observable. This is captured by [Stone's theorem](https://en.wikipedia.org/wiki/Stone's_theorem_on_one-parameter_unitary_groups). 

The most common continuous transformations considered and the Hermitian operators (observables) that generate them are:

::::{tab-set}
:::{tab-item} Time
:sync: tab1

**Unitary:** $U(t) = e^{-\frac{i}{\hbar}~H~t} ~ \forall~t~\in~\mathbb{R}^1$

**Generator:** $H$ - Hamiltonian

**Parameter:** $t$ - time

:::
:::{tab-item} Space
:sync: tab2

**Unitary:** $U(a) = e^{-\frac{i}{\hbar}~P~a}~ \forall~a~\in~\mathbb{R}^1$

**Generator:** $P$ - Momentum 

**Parameter:** $a$ - displacement


:::
:::{tab-item} Rotation 
:sync: tab3

**Unitary:** $U(\theta) = e^{-\frac{i}{\hbar}~L_\alpha~\theta}~ \forall~\theta~\in~\mathbb{R}^1 \mod 2 \pi$

**Generator:** $L_\alpha$ - Angular Momentum in $\alpha \in \{x,y,z\}$ 

**Parameter:** $\theta$ - angle (mod $2\pi$)

::::

For an operator, $B$, to be symmetric with respect to the continuous transformation, generator by the observable $G$, it must be the case that 
\begin{equation}
[ U(q) , B ] = 0, ~ ~ ~  U(q) = e^{-\frac{i}{\hbar}~G~q},
\end{equation}
which is possible if and only if $[G,B] = 0$. 

### Conservation Laws

A value is conserved under a given transformation, $U$, in quantum mechanics, if its expectation value does not change under that transformation. 

When an observable, $A$, was said to be symmetric with respect to a transformation $U$, a consequence was that the expectation value of $A$ did not change if the state being considered was evolved by $U$. 

Hence, symmetries in the physical system lead to conservation laws. This is the fundamental message in the famous [Noether's theorem](https://en.wikipedia.org/wiki/Noether%27s_theorem).  

For example, a closed quantum system with Hamiltonian $H$ evolves in time via the time-evolution operator, $U(t)=e^{-\frac{i}{\hbar}Ht}$. It can be seen that 
\begin{equation}
[U(t), H] = 0 ~~ ~  {\rm as} ~~~ [H,H] = 0,
\end{equation}
meaning that the expectation value of $H$ does not change under time evolution. Hence, energy is conserved under time evolution in closed quantum systems (assuming the Hamiltonian is time-independent). 

In general, given a systems evolves via a unitary $V$ and $[V,H]=0$, then the dynamics described by $V$ are considered to be energy conserving, meaning that neither the expectation value of $H$, nor  the probability of getting each outcome (eigenvalue) of $H$ when measuring the observable, changes under the transformation $V$.    


## States 

A state $\ket{\psi}$ is symmetric with respect to the transformation $U$ if 
\begin{equation}
U \ket{\psi} = e^{i \theta} \ket{\psi},
\end{equation}
for some $ \theta $. As global phases cannot be measured, this means that the state $\ket{\psi}$ is unchanged in any measurable way by the transformation $U$. 

Strictly speaking, the above definition is for invariance with respect to the transformation $U$, with the definition becoming that of symmetry if $ \theta = 0$. However, given a global phase is not physical in the sense that it can never be measured, the two can be used interchangeable. 

### Symmetric and Anti-symmetric states 

Another notion of the symmetry of a quantum state arises when discussing fermions and bosons. Let  
\begin{equation}
\ket{\psi} \in \mathcal{H}_A \otimes \mathcal{H}_B
\end{equation}
be a bipartite state and let $\ket{\psi}_S$ be the state for which the $A$ and $B$ systems have been swapped, $\ket{\psi}_S = {\rm SWAP} \ket{\psi}$. The state $\ket{\psi}$ is symmetric if
\begin{equation}
\ket{\psi}_S =  \ket{\psi},
\end{equation}
and anti-symmetric if 
\begin{equation}
\ket{\psi}_S = -\ket{\psi}.
\end{equation}
This can be seen with the [Bell states](#bell_states_teleportation_target) where 
\begin{align*}
\ket{\Phi_{00}^{+}} &= \frac{\ket{0}_{A}\ket{0}_{B}+\ket{1}_{A} \ket{1}_{B}}{\sqrt{2}}, \\
&= \ket{\Phi_{00}^{+}}_S,
\end{align*}
whereas 
\begin{align*}
\ket{\Phi_{11}^{+}} &= \frac{\ket{0}_{A}\ket{1}_{B}-\ket{1}_{A} \ket{0}_{B}}{\sqrt{2}}, \\
&= - \ket{\Phi_{11}^{+}}_S.
\end{align*}
Hence, $\ket{\Phi_{11}^{+}} $ is antisymmetric whilst the other three two-qubit Bell states are symmetric. 
