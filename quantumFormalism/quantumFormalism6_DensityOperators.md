---
title: Density Operators
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
keywords: States, Density Operators, Density Matrices
abstract: The details of how both quantum and classical uncertainty can be captured in a single model.    
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(density_operator_page_target)=
## Definition 

A density operator, $ \rho $ is a positive semi-definite operator of trace one,
\begin{equation}
\rho \geq 0, ~~ \textrm{tr} \big[ \rho \big] = 1.
\end{equation}

Density operators are vectors in a Hilbert space and are used to model ensembles of quantum states. They allow uncertainty in measurement outcomes arising from both quantum and classical origin's to be modelled.

### Physical Interpretation  

Consider a source emitting a state from the ensemble $( p_i, \ket{\psi_i} )$, meaning the state $ \ket{\psi_i} $ is emitted by the source with probability $ p_i $, $\sum_i p_i = 1$. This ensemble is described by the **density operator** 
\begin{equation}
\rho = \sum_i p_i \ket{\psi_i}\bra{\psi_i},
\end{equation}

where $\ket{\psi_i}\bra{\psi_i}$ is the projector onto the state $ \ket{\psi_i} $. 

When performing a measurement on a state output from the source, there will be uncertainty in the measurement outcomes arising from both the classical uncertainty from it being unknown which state one has and from the quantum nature of the state one does have.

### Properties 
 
1. $\rho^{\dagger} = \rho$, density operators are [Hermitian operators](#hermitian_adjoint_page_target).
2. Given an observable $O = \sum \lambda_k \ket{\lambda_k}\bra{\lambda_k}$. The probability of measuring $O$ and getting the outcome $\lambda_k$ is given by
\begin{equation}
\textrm{prob}(\lambda_k) = \textrm{tr} \big[ \rho \ket{\lambda_k} \bra{\lambda_k} \big] = \bra{\lambda_k} \rho \ket{\lambda_k}.
\end{equation}
3. The positivity of the density operator ensures that all probabilities are positive as, 
\begin{equation} 
\rho \geq 0 \Longleftrightarrow \bra{u} \rho \ket{u} \geq 0~\forall~\ket{u}.
\end{equation}
4. The unit trace of the density operator ensures normalisation, 
\begin{align*}
  \textrm{tr} \big[ \rho \big] &= \textrm{tr} \bigg[ \sum_i p_i \ket{\psi_i} \bra{\psi_i} \bigg] \\
  &= \sum_i p_i \braket{\psi_i | \psi_i} \\
  &= \sum_1 p_i = 1
\end{align*}
4. Different ensembles can lead to the same density operators. Given the density operator is all one needs to calculate possible measurement outcomes, it is impossible to distinguish two sources (two ensembles) with the same density operator. 
5. All density operators have at least one source that could generate it. Specifically, a density operator $ \rho $ can be written in diagonal form as 
\begin{equation}
\rho = \sum_n \lambda_n \ket{\lambda_n}\bra{\lambda_n},
\end{equation}
where $ \lambda_n $ are the eigenvalues of $ \rho $ with associated eigenvectors $\ket{\lambda_n}$. Given that $ \lambda \geq 0$ (due to the positive of $ \rho $) and $ \sum_n \lambda_n = 1$ (due to the unit trace condition) this density operator can be realised by a source outputting the ensemble $( \lambda_n, \ket{\lambda_n})$. 

### Density Matrix 

A density operator written with respect to a particular [basis](#basis_page_target) gives the density matrix. 

Let the set of vectors $ \{ \ket{i} \}_{i=0}^{d-1} $ be a basis. The density matrix of a density operator $ \rho $ with respect to this basis is given by 
\begin{equation}

\rho = \begin{pmatrix}
\bra{0} \rho \ket{0}, \bra{0} \rho \ket{1}, ~ \ldots ~, \bra{0} \rho \ket{d-1} \\
\bra{1} \rho \ket{0}, \bra{1} \rho \ket{1},  ~ \ldots ~, \bra{1} \rho \ket{d-1} \\
\bra{2} \rho \ket{0}, \bra{2} \rho \ket{1}, ~ \ldots ~, \bra{2} \rho \ket{d-1} \\
 \vdots \\
\bra{d-1} \rho \ket{0}, \bra{d-1} \rho \ket{1}, \ldots, \bra{d-1} \rho \ket{d-1} \\
\end{pmatrix}
\end{equation}

## Inner Product 

The Hilbert Schmit inner product, $(\cdot, \cdot): \mathcal{H} \times \mathcal{H} \rightarrow \mathbb{C}^{1}$, is an inner product between two operators. When considered between two density operators $ \rho $ and $ \sigma $ it is given by 
\begin{equation}
(\rho, \sigma) = \textrm{tr} \big[  \rho^{\dagger} \sigma \big]. 
\end{equation}

## Mixed and Pure States 

A source that emits a single quantum state with probability one is describe by a pure state. All uncertainties in measurement outcomes on pure state are therefore only quantum mechanical in origin. 

Put alternatively, a density operator is in general a probabilistic mixture of quantum states. Pure states are then those quantum states that cannot be written as a probabilistic mixture of other quantum states. 

The [convex hull](https://en.wikipedia.org/wiki/Convex_hull) of the set of pure states is the set of density operators. 

A density operator $ \rho $ is pure if and only if 
1. $ \rho $ is a [rank one](#rank_target_linear_maps) projector onto a quantum state $\ket{\psi}$, 
\begin{equation}
\rho = \ket{\psi} \bra{\psi}.
\end{equation}
2. $\textrm{tr} \big[ \rho^2 \big] = 1$. 
    - This leads to a purity measure, with $ \gamma = \textrm{tr} \big[ \rho^2 \big]$, with $ 1/d \leq \gamma \leq 1$, where $\gamma = 1$ if and only if $ \rho $ is pure and $ \gamma = 1/d $ if $ \rho $ is maximally mixed.  



## The Reduced Density Operator  

Consider a state that exists across multiple systems
\begin{equation}
\ket{\Psi}\bra{\Psi} \in \mathcal{H}_A \otimes \mathcal{H}_B.
\end{equation}
The reduced density operator of $A$ is an operator on $\mathcal{H}_A$ that contains all the information about measurement outcomes one could get if measurements were only performed on the part of the state in system $A$. 

The reduced density operator on system $A$ is found by tracing out system $B$, whilst the reduced density operator on system $B$ is found by tracing out system $A$,
\begin{align*}
\rho_A = \textrm{tr}_{B} \big[ \ket{\Psi}\bra{\Psi} \big], \\
\rho_B = \textrm{tr}_{A} \big[ \ket{\Psi}\bra{\Psi} \big],
\end{align*}
where $\textrm{tr}_{\theta}$ an a map known as the partial trace. 

The notion of the reduced density operator can be generalised to any number of systems and also applies to mixed states across multiple systems. 

### Limitations

It is important to note that the reduced density operator does not tell one about the correlations between the system A and B. It only contains information about measurement outcomes from measurements made on the part of the state in the system A. With just $ \rho_A $ one cannot say with certainty what measurement outcomes they would get from measuring the part of the state in system $B$ (they would need $ \rho_B $ for this) or what measurement outcomes they would get from measuring the global state $ \ket{\Psi}\bra{\Psi} $. In addition, the reduced state $ \rho_A $ does not lead to a unique global state, hence, from $ \rho_A $ one cannot find the global state. 

### Properties of the Reduced Density Operator 

1. $\rho_A^{\dagger} = \rho_A$, the reduced density operator is Hermitian. 
2. $\rho_A \geq 0$, the reduced density operator is positive. 
3. $\textrm{tr} \big[ \rho_A \big] = 1$, the reduced density operator has unit trace. 

:::{dropdown} The Partial Trace

The **partial trace** is used to find the reduced density operator and is given by the following map
\begin{equation}
\textrm{tr}_{B} \big[ \ket{i}\bra{j}_A \otimes \ket{l}\bra{k}_B \big] = \braket{k|l}\ket{i}\bra{j}_A.
\end{equation}
Here, one would say they are tracing out system $B$. This means applying the trace operation to only the $B$ system. 

The partial trace is a [quantum channel](#quantum_channel_page_target), and hence it is a linear, completely positive, trace-preserving map. 

The full trace can be decomposed into the partial trace over all the different sub-systems 
\begin{align*}
\textrm{tr} \big[ \ket{\Psi}\bra{\Psi} \big] &= \textrm{tr}_B \bigg( \textrm{tr}_A \big[ \ket{\Psi}\bra{\Psi} \big] \bigg) \\
&= \textrm{tr}_A \bigg( \textrm{tr}_B \big[ \ket{\Psi}\bra{\Psi} \big] \bigg)
\end{align*}

The notion of the partial trace can be generalised to any number of systems. 
:::