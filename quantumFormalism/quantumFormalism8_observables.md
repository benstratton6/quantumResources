---
title: Observables 
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
keywords: Measurements, Hermitian Operators, Eigenvalues, Eigenvectors.  
abstract: The details of how measurements on quantum states are modelled.    
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Definition 

An observables is a physical property that can be measured. 

In quantum mechanics, observables are modelled by [hermitian operators](#hermitian_adjoint_page_target).

In the following all the concepts needed to understand this definition and why it is used will be built up. 

## Hermitian Operators

The [adjoint](#the_adjoint_page_target) of a linear operator $A$, denoted by $A^{\dagger}$, is defined by 
\begin{align*}
\bra{\psi} A^{\dagger} \ket{\phi} = \bra{\phi} A \ket{\psi}^{*},
\end{align*}
where $(\cdot)^*$ is a the complex conjugate and $(\cdot)^{\dagger}$ is the adjoint operator and $\ket{\psi}, \ket{\psi}$ are general states. See [here](#the_adjoint_page_properties) for more properties of the adjoint operator. 

It can be seen from this definition that the matrix of $A^{\dagger}$ is the matrix of $A$ transposed with elements complex conjugated.   

:::{dropdown} Details of This Definition

Let $(\cdot, \cdot): \mathbb{C}^{n} \otimes \mathbb{C}^{n} \rightarrow \mathbb{C}^{1}$ be an inner product, and $A: \mathcal{H} \rightarrow \mathcal{H}$ a linear operator. 
The adjoint of the linear operator $A$, denoted by $A^{\dagger}$, is the operator that satisfies the following relation 
\begin{equation}
(A^{\dagger} \ket{\psi}, \ket{\phi}) = (\ket{\psi}, A \ket{\phi}),
\end{equation}
where $\ket{\psi}, \ket{\phi}~\in~\mathcal{H}$. Explicitly inputting the form of the [inner product](#inner_product_hilbert_space_definition) we are using gives 
\begin{align*}
\big[ \bra{\psi} A^{\dagger} \big] \ket{\phi} = \bra{\psi} \big[ A \ket{\phi} \big],
\end{align*}
where the brackets are used to show which ket the operator is acting upon. Letting 
\begin{equation}
\ket{\phi'} = A \ket{\phi},
\end{equation}
gives 
\begin{align*}
\big[ \bra{\psi} A^{\dagger} \big] \ket{\phi} &= \braket{\psi|\phi'}, \\
&= \braket{\phi'|\psi}^{*}, \\
& = \big[ \bra{\phi} A] \ket{\psi}^{*}.
\end{align*}
where the [properties](#hilbert_space_inner_product_properties) of the inner product have been used. Dropping the brackets gives the definition of the adjoint given in the main text.  
:::

An operator $A$ is said to be Hermitian, or self-adjoint, if 
\begin{equation}
A^\dagger = A.
\end{equation}

### Properties of Hermitian Operators

1. Hermitian operators have real eigenvalues.
2. The eigenvectors of hermitian operators with different eigenvalues are orthogonal.
3. The eigenvectors of hermitian operators form a complete set of basis states. 


:::{dropdown} Proofs of (most) of these properties

Let $A$ be a hermitian operators acting on a Hilbert space. 

1. **Hermitian operators have real eigenvalues:**
The [eigenvalue equation](#eigenvalues_page_target) in terms of bra-ket notion is 
\begin{equation}
A \ket{a} = a \ket{a},
\end{equation}
where $a$ is the eigenvalue of the eigenvector $\ket{a}$. 

Inputting an eigenvector of $A$ into the definition of the adjoint with a hermitian operator gives 
\begin{align*}

\bra{a} A \ket{a} = \bra{a} A \ket{a}^{*},

\end{align*}
as $A^\dagger = A$. 

The left hand side of this equation gives 
\begin{align*}
\bra{a} A^{\dagger} \ket{a} &= \bra{a} a \ket{a}, \\
&= a \braket{a|a}, \\
&= a. 
\end{align*} 

The right hand side of this equation gives 
\begin{align*}
\bra{a} A \ket{a}^* &= \bra{a} a \ket{a}^*, \\
&= a* \braket{a|a}^*, \\
&= a^*. 
\end{align*} 
Hence, $a=a^*$ meaning $a$ must be a real number. 

2. **The eigenvectors of hermitian operators with different eigenvalues are orthogonal:** Consider two eigenvectors of $A$ given by 
\begin{equation}
A \ket{a} = a \ket{a}~~ \textrm{and} ~ ~ A \ket{a'} = a' \ket{a'},
\end{equation}
such that $a \neq a'$. Inputting them into the definition of the adjoint gives 
\begin{align*}
\bra{a'} A \ket{a} = \bra{a} A \ket{a'}^{*},
\end{align*}
which can be rewritten as  
\begin{align*}
(a-a')\braket{a'|a} = 0.
\end{align*}
Given $a \neq a'$ it must be the case that $\braket{a'|a} = 0$.

3. **The eigenvectors of hermitian operators form a complete set of basis states:** This result is given by the spectral theorem which says that an operator $A$ acting on $\mathcal{H}^d$ is normal, meaning $A^\dagger A = A A^\dagger$ (which is satisfied by all hermitian operators), if and only if it is diagonalisable in some [othronormal basis](#Orthonormal_Basis_basis_target). 

Hence, $A$ can be written as 
\begin{equation}
A = \sum^{d-1}_{i=0} \lambda_i \ket{\lambda_i}\bra{\lambda_i},
\end{equation}
where 
\begin{equation}
A \ket{\lambda_i} = \lambda_i \ket{\lambda_i} ~ \forall~i
\end{equation}
and 
\begin{equation}
\braket{i|j} = \delta_{ij}~\forall~i,j.
\end{equation}

This means $A$ can always be written as a diagonal operator with respect to it's orthonormal eigenbasis. 

It could be the case that $\lambda_i = \lambda_j$ for some values of $i,j$. In this case the eigenvalues are said to be degenerate. In this case, $A$ can be written as 
\begin{equation}
A = \sum_{i} \lambda_i P_{i},
\end{equation}
where $P_{i}$ is the [projection](#projections_linear_maps_target) onto the eigenspace with eigenvalue $\lambda_i$ (meaning the Hilbert space spanned by the set of eigenvectors with eigenvalue $\lambda_i$). Hence, if 
\begin{equation}
A \ket{\kappa_j} = \lambda_i \ket{\kappa_j}
\end{equation}
for all vectors in the set $\{ \ket{\kappa_j} \}_j^{k\leq d}$ then 
\begin{equation}
P_{i} = \sum_j^{k} \ket{\kappa_j}\bra{\kappa_j}. 
\end{equation}

:::

## Measuring Observables

The possible outcomes of measuring an observables $A$ are the eigenvalues of $A$. 

After measuring the observables $A$ and getting the eigenvalue $ \lambda $, for example, the state the measurement was performed on will be in the eigenspace spanned by the eigenvectors with eigenvalue $a$.  

Quantum mechanics does not tell us which outcome *will* occur as a result of measuring an operator, it only tells us the *probabilities* of getting each possible outcome. After measuring $A$ on a state, the output is a random variable where the outcome is $ \lambda $ with some probability $P(\lambda)$.  

Let $A$ be an observable such that
\begin{equation}
A = \sum_{i} \lambda_i P_{i},
\end{equation}
where $P_i$ is the projection onto the eigenspace of $A$ with eigenvalue $\lambda_i$, and $\ket{\psi}\in\mathcal{H}$. 

**Probabilities of Measurement Outcomes:** the probability of measuring the observable $A$ on $\ket{\psi}$ [💭](#Probability_Notation_equation) and getting the outcome $\lambda_i$ is 
\begin{equation}
P(\lambda_i \vert A) = \bra{\psi} P_i \ket{\psi}.
\end{equation}
If the eigenspace of $\lambda_i$ is not dengerate, then $P_i$ is just the projection onto the eigenstate of $A$ with eigenvalue $\lambda_i$, meaning $P_i = \ket{\lambda_i}\bra{\lambda_i}$, and hence, 
\begin{equation}
P(\lambda_i | A) = \vert \braket{\lambda_i|\psi} \vert ^ 2.
\end{equation}

Let $\{ \lambda_i \}_{i=0}^{d-1}$ be the eigenvectors of a hermitain operator $A$. Given this set of vectors forms an orthonormal basis a state $ \ket{\psi} $ can be decomposed in this basis,
\begin{align*}
\ket{\psi} = \sum_i p_i \ket{\lambda_i},
\end{align*}
where $p_i = \braket{\lambda_i|\psi}$. It can therefore be seen that $\vert p_i \vert ^2$ gives the probability of measuring $A$ on $\ket{\psi}$ and getting the outcome $\lambda_i$. 

Therefore, when considering measuring the observable $A$ on a state $\psi$, one should first decompose the state $\ket{\psi}$ in the eigenbasis of $A$. The coefficients of the decomposition can then be used to find the probabilities of getting the different measurement outcomes. Note, when measuring the observable $A$ one should **not** apply the observable to the state. 

**State After Measurement:** after measuring an observable $A$ on the state $\ket{\psi}$ and getting the outcome $\lambda_i$ the post measurement state, $\ket{\psi_{\rm post}}$, is the state $\ket{\psi}$ projected into the eigenspace of the $A$ with eigenvalue $\lambda_i$,
\begin{align*}
\ket{\psi_{\rm post}} &= \frac{P_{i} \ket{\psi}}{ \vert \vert P_i \ket{\psi} \vert \vert_2}, \\
&= \frac{P_{i} \ket{\psi}}{ \sqrt{P(\lambda_i | A)} }
\end{align*}
where $ \vert \vert \cdot \vert \vert_2$ is the [2-norm](#l2_norm_norms_page_target) and ensures the post measurement state is normalised - and hence a valid state. The second line can be shown as
\begin{align*}
\vert \vert P_i \ket{\psi} \vert \vert_2 &= \sqrt{ \vert  P_i \ket{\psi} \vert }, \\
&= \sqrt{ \big( \bra{\psi} P_i^{\dagger} \big) \big(P_i \ket{\psi} \big) }, \\
&= \sqrt{ \big( \bra{\psi} P_i \big) \big(P_i \ket{\psi} \big) }, \\
&= \sqrt{ \bra{\psi} P_i \ket{\psi}  }, \\
&= \sqrt{ P(\lambda_i | A) },
\end{align*}
where we have used the fact that projection operators onto eigenspaces of hermitian operators are hermitian, $P_i^{\dagger}=P_i$ and $P_i^{2} = P_iP_i = P_i$. 

**Expectation Values:** the expectation value of an observable is the average outcome one would expect if measuring $A$ on many copies of a state, 
\begin{align*}
\braket{A} = \sum_i \lambda_i P(\lambda_i \vert A),
\end{align*} 
which is the probability of getting the outcome $\lambda_i$ multiplied by the outcome itself, summed over all possible outcomes from measuring $A$. 

The expectation value of $A$ on $\ket{\psi}$ has a succinct form as 
\begin{align*}
\braket{A} &= \bra{\psi} A \ket{\psi}, \\
&= \bra{\psi} \biggl( \sum_{i} \lambda_i P_{i} \biggl) \ket{\psi}, \\
&= \sum_i \lambda_i \bra{\psi} P_i \ket{\psi}, \\
&= \sum_i \lambda_i P(\lambda_i \vert A).
\end{align*}

Higher moments of expectation values can also be found as 
\begin{align*}
\braket{A^2} &= \bra{\psi} A^2 \ket{\psi}, \\
&= \sum_i \lambda_i^2 P(\lambda_i \vert A),
\end{align*}
which generalises to the $n$th moment as expected. 

From this, the standard deviation can be found as
\begin{align*}
\sigma_{A} = \sqrt{\braket{A^2} - \braket{A}^2},
\end{align*}
which can be interpreted as the standard deviation of the measurement outcomes if the observable $A$ is measured on many copies of $\ket{\psi}$.  

## The Uncertainty Principle

## Why Hermitian Operators as Observables

In this section we will aim to motivate why hermitian operators should be used to represent things that can be measured in quantum mechanics. So reasoning commonly found in the literature is given. 

1. **They give real measurement outcomes**. As proved above, the eigenvalues of Hermitian matrices are real. Given the eigenvalues of an observables are the possible measurement outcomes one can get, this means that all possible measurement outcomes, for all possible things that can be measured, are real. In [The Principles of Quantum Mechanics](https://philarchive.org/rec/DIRTPO), Dirac argues that all possible measurement outcomes must be real due to the potential for the measurement of an observables to alter the state (e.g the post measurement state becomes an eigenstate of the observable measured). If one were to try and measure a complex number associated to a quantum state, they would need two real numbers to specify it. The observer could try and measure the real and imaginary part separately. However, in general, performing a measurement to extract the real part will alter the state, changing what one would get if they then performed a measurement to extract the imaginary part. For this reason, Dirac claims that all measurement outcomes must be real. 

2. **Repeat Measurements** 
3. **Retains probability**






