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
(quantum_state_page_target)=
## Definition 

A quantum state is modelled as a vector in a complex [Hilbert space](#hilbert_space_target). 

### Ket's

In [Dirac notation](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation), A quantum state is denoted via a ket,
\begin{equation}
\ket{\psi} ~ \in ~\mathcal{H},
\end{equation}
where $ \psi $ is just some label and $\mathcal{H}$ is a Hilbert space. 

This is a universal way to represent quantum states that is independent of the underlying Hilbert space upon which it is defined e.g. if the Hilbert is finite or infinite dimensional. In addition, it is a basis independent way to represent the quantum state. 

**Properties**
1. Given quantum states are vectors in a vector space, any linear combination of 
quantum states is also a quantum state. This give the principal of superposition, where one would say $\ket{\phi}~\in~\mathcal{H}$ is in a superposition of states $\ket{\psi_1}, \ket{\psi_2}, \ldots, \ket{\psi_n}~\in~\mathcal{H}$ if there exists a set $\{\alpha_i: \alpha_{i}~\in~\mathbb{C}^1~\forall~n \}_{i=1}^{n}$ such that
\begin{equation}
\ket{\phi} = \alpha_1 \ket{\psi_1} + \alpha_2 \ket{\psi_2} \ldots + \alpha_n \ket{\psi_n}.
\end{equation}

2. One can find sets of basis vectors for $\mathcal{H}$, $\{ \ket{i} \}_{i=0}^{d-1}$, such that any state in the space $\ket{\psi}~\in~\mathcal{H}$ can be written as a superposition over those basis elements,
\begin{equation}
\ket{\psi} = \sum_{i=0}^{d-1} \psi_i \ket{i}, ~\textrm{where} ~ \psi_i~\in~\mathbb{C}^{1}~\forall~i.
\end{equation}

3.  let $\alpha_1, \alpha_2 \in~\mathbb{C}^{1}$ and $\ket{\psi}~\in~\mathcal{H}$, then $\alpha_1 \ket{\psi} + \alpha_2 \ket{\psi} = \ket{\psi}$ unless $\alpha_1 + \alpha_2 = 0$. 
    - From this, one reaches the important point that a ket vector multiped by any complex number that is not zero, gives the same ket vector. 

### Bra's

The Hilbert space in which quantum states are defined has a [dual space](#dual_vector_spaces_target) $\mathcal{H}^{*}$, with elements of this dual space denoted by bra's,
\begin{equation}
\bra{\psi}~\in~\mathcal{H}^{*}.
\end{equation}

This dual vector space is the space of linear functionals mapping elements in $\mathcal{H}$ to the scalars $\mathbb{C}^{1}$. Note, there is a one to one correspondence between elements in the space $\mathcal{H}$ and elements in the dual space $\mathcal{H}^{*}$. 

The conjugate transpose of a ket gives it's associated bra,
\begin{equation}
\big( \ket{\psi} \big)^{\dagger} = \bra{\psi}.
\end{equation}

**Properties**
1. Let $\alpha~\in\mathbb{C}^{1}$. The bra of $\alpha \ket{\psi}$ is given by $\big(\alpha \ket{\psi} \big)^{\dagger} = \bra{\psi} \alpha^{*}$, where $(\cdot)^{*}$ is the complex conjugate. 
2. Let $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$, the bra of $\ket{\psi}$ is $\bra{\psi} = \alpha^{*} \bra{0} + \beta^{*} \bra{1}$. 

### Inner Product

A [Hilbert space](#hilbert_space_target) is an [inner product](#inner_product_target_definition_inner_product_space) space, with the inner product, $(\cdot, \cdot): \mathcal{H} \times \mathcal{H} \rightarrow \mathbb{C}^{1}$, defined as 
(inner_product_hilbert_space_definition)=
\begin{equation}
(\ket{\psi}, \ket{\phi}) = \braket{\psi|\phi}~\in~\mathbb{C}^{1}.
\end{equation}

This inner product satisfies all the conditions of an inner product in a vector space:
(hilbert_space_inner_product_properties)=
1. $\braket{\psi|\psi} \geq 0$
    - Positive-definiteness
2. $\braket{\psi|\phi} = \braket{\phi|\psi}^{*}$
    - Conjugate symmetry
3. $ \bra{\psi} \big( \alpha_1\ket{\phi_1} + \alpha_2 \ket{\phi_2} \big)  = \alpha_1 \braket{\psi|\phi_1} + \alpha_2 \braket{\psi|\phi_2}$ 
    - Additivity and Linearity in the second argument

**Interpretation of Inner Product** 

Colloquially, the inner product measures the 'overlap' between the two quantum states $\ket{ \psi}$ and $\ket{\phi}$. 

More formally, the inner product between two states, $\ket{ \psi}$ and $\ket{\phi}$, gives the probability amplitude of making a measurement on $\ket{\psi}$ and finding the state in $\ket{\phi}$. The square of the probability amplitude then gives the probability. Hence, the probability of observing the state $\ket{\psi}$ to be in the state $\ket{\phi}$ is given by 
\begin{equation}
\vert \braket{\phi | \psi} \vert^{2}. 
\end{equation}

**Properties**
1. Two states, $\ket{\psi}$ and $\ket{\phi}$, are said to be **orthogonal** if their inner product is zero, $\braket{\psi | \phi} = 0$. 
(normalised_quantum_states_target)=
2. The inner product induces a norm, $ \vert \vert \ket{\psi} \vert \vert = \sqrt{\braket{\psi | \psi}}$. All valid quantum states are those such that $ \vert \vert \ket{\psi} \vert \vert = 1$. This is known as normalisation and ensures that the probability of observing the state $\ket{\psi}$ to be in the state $\ket{\psi}$ is one.


## States as Column Vectors 

The smallest quantum systems are states of dimension $2$, known as qubits (quantum bits). They are model by vectors in a Hilbert space defined over $\mathbb{C}^{2}$, where $\mathbb{C}$ are the complex numbers. Hence, one can write the state of a qubit $\ket{\psi}$ as 
\begin{equation}
\ket{\psi} = \begin{pmatrix} \alpha \\ \beta \end{pmatrix} ~ \in ~ \mathcal{H}^{2},
\end{equation}
where $\alpha, \beta~\in~\mathbb{C}^{1}$. 

Note, when writing a column vector, one must do so with respect to a given [basis](#basis_page_target), meaning the column vector of a quantum state is not unique. Vectors of a basis can also be written as kets, as seen above, with the [standard basis](#standard_basis_basis_target) in $2$ dimensions denoted in terms of kets as
\begin{equation}
\ket{0} = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, ~ ~ ~ \ket{1} = \begin{pmatrix} 0 \\ 1 \end{pmatrix}.
\end{equation}
The state $ \ket{\psi} $ written with respect to the standard basis is then
\begin{align*}
\ket{\psi} &= \alpha \begin{pmatrix} 1 \\ 0 \end{pmatrix} + \beta \begin{pmatrix} 0 \\ 1 \end{pmatrix} \\
&= \alpha \ket{0} + \beta \ket{1}.
\end{align*}

Bra's are then given by row vectors. Consider 
\begin{align*}
\bra{\psi} &= \big( \ket{\psi} \big)^{\dagger} \\
&= \big( \alpha \ket{0} + \beta \ket{1} \big)^{\dagger} \\
&= (\alpha \ket{0})^{\dagger} + (\beta \ket{1})^{\dagger} \\
&= \bra{0} \alpha^* + \bra{1} \beta^* \\
&= (1,0) \alpha^* + (0,1) \beta^*,
\end{align*}
where 
\begin{equation}
\bra{0} = (1,0) ~ ~ ~ \bra{1} = (0,1)
\end{equation}


Given the standard basis is an [orthonormal basis](#Orthonormal_Basis_basis_target), the inner product between states in the basis obey
\begin{align*}
\braket{i|j} = \delta_{ij}.
\end{align*}
The coefficients $ \alpha $ and $ \beta $ can then be found using the inner product as 
\begin{align*}
\alpha = \braket{0 | \psi}, \\
\beta = \braket{1 | \psi}. 
\end{align*}

The inner product between two states can be evaluated in terms of the column and row vectors by expanding the states in terms of the same basis. 

:::{dropdown} Details 


Consider an orthonormal basis of $\mathcal{H}$ given by $ \{ i \}_{i=0}^{d-1}$. The identity operator can be written as 
\begin{equation}
\mathbb{I} = \sum_{i=0}^{d-1} \ket{i}\bra{i},
\end{equation}
meaning the identity can be written as the sum over all elements in the basis. 

The inner product between $\ket{\psi}$ and $\ket{\phi}$ is then 
\begin{align*}
\braket{\phi | \psi} &= \bra{\phi} \mathbb{I} \ket{\psi}, \\
&= \bra{\phi} \bigg( \sum_{i=0}^{d-1} \ket{i}\bra{i} \bigg) \ket{\psi} \\
&= \sum_{i=0}^{d-1} \phi_{i}^{*} \psi_{i} \\
&= (\phi_0, \phi_1, \ldots, \phi_{d-1}) \begin{pmatrix} \psi_0 \\ \psi_1 \\ \vdots \\ \psi_{d-1} \end{pmatrix}
\end{align*}
where $\phi_{i} = \braket{ i | \phi }$ and $\psi_{i} = \braket{ i | \psi}$ are the coefficients of the decomposition of $\ket{\phi}$ and $\ket{\psi}$ respectively in the basis $ \{ i \}_{i=0}^{d-1}$. 
:::
<!-- General quantum states of finite dimensional $d$ are then modelled as vectors in a Hilbert space defined over $\mathbb{C}^{d}$. If the standard basis is given by the set of ket vectors $\{ \ket{i} \}_{i=0}^{d-1}$ then any state in the space $ \ket{\psi} $ can be decomposed into this basis as 
\begin{equation}
\ket{\psi} = \sum_{i} \psi_i \ket{i},
\end{equation}
where $\psi_i~\in~\mathbb{C}^{1}$ are coefficients given by 
\begin{equation}
\psi_{i} = \braket{i|\psi},
\end{equation}
given the standard basis is an [orthonormal basis](#Orthonormal_Basis_basis_target) meaning $\braket{i|i} = \delta_{ij}$. -->