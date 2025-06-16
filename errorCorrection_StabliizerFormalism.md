---
title: Stabilizer Formalism 
subject: Tutorial
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
keywords: qubits, Repetition Code, bit-flips, phase errors.  
abstract: The stabilizer formalism of quantum error correction.   
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

The stabilizer formalism is a method for creating error correcting codes using the Pauli-group. In addition to allowing certain errors to be detected and correct, logical gates can also be performed in this framework. 

## Pauli-group 

The generators of the qubit Pauli-group are
\begin{equation}
\mathcal{P}_1 = \langle X, Z, i\mathbb{I} \rangle.
\end{equation}
From these operators all elements of the one qubit Pauli-group can be generated. The Pauli-group is the set of Pauli-operators plus identity with all possible phases of $\{\pm 1, \pm i \}$. 

The $n$-qubit Pauli-group , $\mathcal{P}_n$, is then the $n$-fold tensor product of elements in the one qubit Pauli-group. All elements in $\mathcal{P}_n$ either commute or anit-commute,
\begin{equation}
P_1P_2 = (\pm)P_2P_1 ~~ \forall ~ ~ P_1, P_2~\in~\mathcal{P}_n,
\end{equation} 

All elements of the Pauli-group have eigenvalues $\{+1, -1\}$ or $\{+i, -i\}$. Here, we mostly consider just the elements with eigenvalues $\{+1, -1\}$ (the Hermitian elements of the Pauli-group). 

## Stabilizer Codes

### Definition

The stabilizers of an error correcting code are defined as 
\begin{equation}
\mathcal{S} = \big\{ P_i \in \mathcal{P}_n: P_i \ket{\psi}_L = \ket{\psi}_L~\forall~\ket{\psi}_L \wedge [P_i, P_j] = 0 ~ \forall ~ (i,j) \big\},
\end{equation}
such that $-\mathbb{I} \notin \mathcal{S}$. The stabilizers are therefore an [Abelian subgroup](#Abelian_group_target_glossary) of the $n$-qubit Pauli-group, $\mathcal{P}_n$, such that all logical states (states in the code space) are $(+1)$ eigenstates of each stabilizer, that does not contain the negative identity operator. 

The justification of these conditions are as follows:

1. $P_i \ket{\psi}_L = \ket{\psi}_L~\forall~\ket{\psi}_L$:
    
    This avoids any logical information encoded in the code space being destroyed when a stablizer is measured on $\ket{\psi}_L$.

    :::{dropdown} Further Details

    A state, $\ket{\omega}$ is said to be stabilized by an operator $U$ if $U\ket{\omega} = \ket{\omega}$, meaning $\ket{\omega}$ is a $(+1)$ eigenstate of $U$. 
    
    From the above definition of $\mathcal{S}$, it can be seen that $\forall~P_i \in \mathcal{S}$ all logical states $\ket{\psi}_L$ are stabilized by $P_i$. Therefore, if one were to measure or apply $P_i$ on any logical state $\ket{\psi}_L$ they would return the state $\ket{\psi}_L$ unchanged. This avoids any logical information encoded in the code space being destroyed when a stablizer is measured on $\ket{\psi}_L$. (Does it also prevent loss of logical information in general? I am currently not sure). 
    
    One can reverse this definition, and defined the code space to be the subspace of the total Hilbert space that is stabilized by all elements of $\mathcal{S}$. Phrased alternatively, the code space is defined as the intersection of all $(+1)$ eigenspaces of the elements of $\mathcal{S}$.  
    :::

2. $[P_i, P_j] = 0$:

    If this condition is not met, only the trivial space can be stabilized. 

    :::{dropdown} Proof
 
    Let $P_i, P_j \in \mathcal{P}_n$ such that $[P_i, P_j] \neq 0$. Moreover, assume they both stabilize $\ket{\psi}_L$ such that 
    \begin{equation}
    P_i \ket{\psi}_L = P_j \ket{\psi}_L = \ket{\psi}_L.
    \end{equation}

    Firstly, note that given that all elements of $\mathcal{P}_n$ commute or anti-commute,
    \begin{equation}
    [P_i, P_j] \neq 0  \implies P_iP_j + P_jP_i = 0.
    \end{equation}
    Secondly, the products, $P_iP_j$ and $P_jP_i$ also stabilize $\ket{\psi}_L$ if $P_i$ and $P_j$ individually stabilize $\ket{\psi}_L$, such that 
    \begin{align*}
    P_iP_j \ket{\psi}_L &= \ket{\psi}_L, \\
    P_jP_i \ket{\psi}_L &= \ket{\psi}_L.
    \end{align*}

    Putting these facts together implies that 
    \begin{align*}
    P_jP_i \ket{\psi}_L &= - P_iP_j \ket{\psi}_L, \\
    &=  - \ket{\psi}_L, \\
    &= \ket{\psi}_L. 
    \end{align*}
    This is only true if $\ket{\psi}_L = 0$, meaning that non-[Abelian subgroups](#Abelian_group_target_glossary) of $\mathcal{P}_n$ can only stabilize a trivial subspace. 

    (Note, the equation $\ket{\psi}=-\ket{\psi}$ is about the physical equivalence of vectors in a Hilbert space, with this equation only being satasfied for the zero vector. It is not about whether two states are physically distinguishable under global phases.)

    :::

3. $- \mathbb{I} \notin \mathcal{S}$: 

    If this condition is not met, only the trivial space can be stabilized.  

    :::{dropdown} Proof
 
    All states are stabilized by $\mathbb{I}$, 
    \begin{equation}
      (\mathbb{I} ) \ket{\psi}_L = \ket{\psi}_L.
    \end{equation}
    Hence, $\mathbb{I} \in \mathcal{S}$ for all possible $\mathcal{S}$. 
    
    If one assumes that $-\mathbb{I} \in \mathcal{S}$, then one needs 
    \begin{equation}
    \big( - \mathbb{I} \big) \ket{\psi}_L = \ket{\psi}_L,
    \end{equation}
    by definition of $\mathcal{S}$. Combining these two facts implys that 
    \begin{equation}
    \ket{\psi}_L = - \ket{\psi}_L, 
    \end{equation}
    which is only true if $\ket{\psi}_L = 0$, meaning that $\mathcal{S}$ would only stabilize a trivial subspace. 

    :::

### Operation 

A stablizer code works by first encoding a logical state into a subspace. Each stablizer in the set $\mathcal{S}$ is then measured, with each measurement giving an output of $+1$ or $-1$. From these measurement outcomes one can establish if an error from a given set has occurred and offer a method to correct it. 

We will work through the logic of these codes step by step. 

#### Preliminaries 

An error correcting code is defined by first establishing a set of code words. These are typically a set of orthogonal pure states $ \{ \ket{i} \}_{i=0}^{N}$ such that $\braket{i | j}=\delta_{i,j}$. The code space, $\mathfrak{C}_L$, is then the subspace of the full Hilbert space, $\mathcal{H}$, spanned by the set of code words,
\begin{equation}
\mathfrak{C}_L = { \rm Span }\big\{ \{\ket{i}\}_{i=0}^N \big\} \subsetneq \mathcal{H}.
\end{equation}
The logical state is then some state encoded within this code space, $\ket{\psi}_L \in \mathfrak{C}_L$. We define $\Pi_L$ to be the projector onto the code space. 

If some unitary error, $U$, acts on the logical state, the state will be mapped to the space spanned by $U$ acting on the code words,
\begin{equation}
U \ket{\psi}_L \in {\rm Span} \big\{ \{ U \ket{i} \}_{i=0}^{N} \big\} = \mathfrak{C}_U \subseteq \mathcal{H},
\end{equation}
where we define this subspace $\mathfrak{C}_U$ and the projector onto the space as $\Pi_{U}$. The goal of an error correcting code is then to (a) determine which of $\mathbb{I}$ or $U$ has been applied to the logical state without (b) disturbing the logical state and hence the encoded information. 

Criteria (a) can be considered as an example of quantum channel discrimination, where the logical state is the reference state, with the added constraint of criteria (b). 

:::{dropdown} Error Correction as Quantum Channel Discrimination

In the task of quantum channel discrimination one considers two parties, Alice and a referee. The referee has some reference state, $\rho_R$, and a predetermined set of quantum channels $\{ \mathcal{E}_i \}_{i=0}^{M}$. Both the reference state and the set of quantum channels are known to Alice.  

The referee chooses an index $j \in [0,M]$ and then applies the channel $\mathcal{E}_j \in \{ \mathcal{E}_i \}_{i=0}^{M}$ to the reference state. The referee then sends the state, $\mathcal{E}_j(\rho_R)$, to Alice. Alice makes a measurement on the state with the intention of identify the channel the referee applied to the reference state. The output of the measurement will therefore be some index $k \in [0, M]$, such that if $k=j$ Alice has succeed in the task and if $k \neq j$ she has failed.

```{figure} error_correction_EC_as_channel_discrimination.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: quantum_channel_discrimination

A schematic of a quantum channel discrimination task. R and A are the referee and Alice respectively. The referee applies a channel from a predetermined set to the reference state and then sends it to Alice. Alice performs a measurement on the state and aims to identify which channel the referee applied. 

```

With some added constraints, error correction can be reframed as a quantum channel discrimination task. The reference state is no-longer a predetermined state but rather an arbitrary state within some predetermined subspace. The referee is then the noise, with it being assumed that the noise is restricted to some likely set of possible channels. Finally, Alice is the decoder of the error correction protocol aiming to identify with error has occurred.  

The major addition to quantum error correction is the need for the logical information encoded into the subspace to not be disturbed by the measurement made by Alice (the decoder). Practically, this means a restriction on the measurements Alice is allowed to perform.   

:::

It is a well known result in quantum information theory that for two quantum states to be deterministically distinguishable they must be orthogonal. Here, we are not concerned with specific states, but rather arbitary states encoded into subspaces. However, the result instead just applies the the subspaces. Hence, it is only possible to deterministically determine if $\mathbb{I}$ or $U$ has been applied to the logical state if 
\begin{equation}
\Pi_{L} \Pi_{U} = 0,
\end{equation}
meaning that for any arbitrary state $\ket{\psi}_L \in \mathfrak{C}_L$, $\bra{\psi}_L U \ket{\psi}_L=0$. 

If this first condition is met it is always the case that one can find a projector $\Pi_R$, such that 
\begin{equation}
\Pi_L + \Pi_U + \Pi_R = \mathbb{I}, 
\end{equation}
where $\Pi_R$ is the projector onto the reminder of the Hilbert space not covered by $\Pi_L$ and $\Pi_U$. This will defined a subspace orthogonal to both $\mathfrak{C}_L$ and $\mathfrak{C}_U$. From here, one can therefore defined an observable
\begin{equation}
O = \lambda_L \Pi_L + \lambda_U \Pi_U + \lambda_R \Pi_R,
\end{equation}
the fulfils both criteria (a) and (b). 

If one has the state $\ket{\psi}_L$, meaning $\mathbb{I}$ has been applied, upon measuring $O$ they will get the outcome $\lambda_L$ with certainty. Hence, if they get the outcome $\lambda_L$ they know the $\mathbb{I}$ has been applied with certainty, satisfying criteria (a). Moreover, given the operator projects into the whole codespace,
\begin{equation}
\Pi_L \ket{\psi}_L = \ket{\psi_L}~\forall~\ket{\psi}_L \in \mathfrak{C}_L,
\end{equation}
the state remains unchanged by the measurement, satisfying criteria (b). If one instead has the state $U\ket{\psi}_L$, meaning $U$ has been applied, upon measuring $O$ they will get the outcome $\lambda_U$ with certainty and hence they can be sure $U$ was applied if they get this outcome. The post measurement state will also be $U \ket{\psi}_L$, meaning an application of $U^\dagger$ will correct the error.

#### Correctable Errors 



#### The Role of the Stabilizers

Given the set of stabilizers is defined for an arbitrary state within the code space, the set of stablizers should be thought of as stabilizing the code space rather than a given logical state. In reality, the code space is defined in the opposite direction: each stabliser, $P_i$, is an element of the Pauli-group and can hence be written as
\begin{equation}
P_i = \Pi^i_{+1} - \Pi^i_{-1} 
\end{equation}
where $\Pi^i_{+1}$ is the projector onto the $+1$ eigenspace $P_i$, and $\Pi^i_{-1}$ the projector onto the $-1$ eigenspace. One can then defined the code space, via the projector on the space $\Pi_{\mathfrak{C}_L}$, as 
\begin{equation}
\Pi_{\mathfrak{C}_L} = \cap_{i=0}^{\vert \mathcal{S} \vert} \Pi^i_{+1}.
\end{equation}


### Measuring Stabilizer 

All elements of $\mathcal{P}_n$ are [unitary](#target_unitary_adjoint_page_unitary_definition). If $P \in \mathcal{P}_n$ is also [Hermitian](#hermitian_adjoint_page_target), then any stabilizer $P$ can be measured on the logic state indirectly, with the measurement outcome stored in an ancilla [💭](#anti_hermitain_pauli_stab_measures_target_glossary).

```{figure} errorCorrectionStabMeasureCircuit.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: stab_measure_circuit_target

A schematic of the circuit used to measure the stabilizer $P$ on the logical state $\ket{\psi}_L$. 
```

Assume that $P \in \mathcal{P}_n$ is a stabilizer of the logical state $\ket{\psi}_L$ such that $P \ket{\psi}_L = \ket{\psi}_L$. Let $E$ be some correctable error that has occurred on the logical state, such that $P ( E \ket{\psi}_L) = E \ket{\psi}_L$ or $P ( E \ket{\psi}_L) = - E \ket{\psi}_L$, depending on whether $E \ket{\psi}_L$ is in the positive or negative eigenspace of $P$. 

The input state into the circuit is $E\ket{\psi}_L \ket{0}_A$, where $A$ labels the ancillary space and the $L$ subscript now doubles as a label for the space of the logical state.  

The output state is then 
\begin{equation}
\frac{1}{2} \big( \mathbb{I}_L \otimes \mathbb{I}_A + P_L \otimes \mathbb{I}_A) E \ket{\psi}_L \ket{0}_A + \frac{1}{2} \big( \mathbb{I}_L \otimes \mathbb{I}_A - P_L \otimes \mathbb{I}_A) E \ket{\psi}_L \ket{1}_A.
\end{equation}

:::{dropdown} Proof

The input state to the circuit is 
\begin{equation}
E\ket{\psi}_L \otimes \ket{0}_A.
\end{equation}
The controlled stabilizer gate can be written as 
\begin{equation}
P_LC_A = \mathbb{I}_L \otimes \ket{0}\bra{0}_A + P_L \otimes \ket{1}\bra{1}_A.
\end{equation}
The output state of the circuit is then 
\begin{align*}

&(\mathbb{I} \otimes H) P_L C_A (\mathbb{I} \otimes H) \big(E\ket{\psi}_L \otimes \ket{0}_A \big) \\
=& (\mathbb{I} \otimes H)\big(\mathbb{I}_L \otimes \ket{0}\bra{0}_A + P_L \otimes \ket{1}\bra{1}_A \big)\big(E \ket{\psi}_L \otimes \ket{+} \big) \\
=& \frac{1}{\sqrt{2}}(\mathbb{I} \otimes H) \big( E\ket{\psi}_L \otimes \ket{0} + PE\ket{\psi}_L \otimes \ket{1}   \big) \\
=& \frac{1}{\sqrt{2}}\big( E\ket{\psi}_L \otimes \ket{+} + PE\ket{\psi}_L \otimes \ket{-}   \big).\\
\end{align*}
Expanding $\ket{+}$ and $\ket{-}$ in the computational basis and factorising completes the proof. 
:::

Therefore, if $P ( E \ket{\psi}_L) = E \ket{\psi}_L$, the second term will go to zero and the output state becomes 
\begin{equation}
E \ket{\psi}_L \ket{0}_A,
\end{equation}
such that if one measures $Z$ on the ancilla they will get the outcome $+1$ (syndrome bit $0$) with certainty. 

If $P ( E \ket{\psi}_L) = - E \ket{\psi}_L$, the first term will go to zero and the output state becomes 
\begin{equation}
E \ket{\psi}_L \ket{1}_A,
\end{equation}
such that a $Z$ measurement performed on the ancilla now gives the outcome $-1$ (syndrome bit $1$) with certainty. 

By performing the above circuit and measuring the ancilla one can therefore determine if the logical state is in the $+1$ or $-1$ eigenspace of the stabilizer $P$. 

Note, this method of performing measurements only really works for measuring observables in $\mathcal{P}_n$ on stabilizer states.

:::{dropdown} Parity Measurements Circuits

When discussing the [2-bit repetition code](#target_error_correction_2_bit_repetition_code) it was noted that the measurement of the stabilizer was akin to performing a parity check on the qubits. Specifically, a logical qubit was encoded into space ${\rm Span}\{ \ket{00}, \ket{11}\}$ such that 
\begin{equation}
\ket{\psi}_L = \alpha \ket{00} + \beta \ket{11}, ~ ~ \vert \alpha \vert^2 + \vert \beta \vert^2=1.
\end{equation}
It was then seen that it was possible to perform error detection on the set of errors $\{\mathbb{I}, X_1, X_2 \}$ by measuring the stabilizer $Z_1 \otimes Z_2$. If $\mathbb{I}$ occurs, the state stays in the code space and measuring the stabilizer gives the output $+1$ (syndrome bit $0$). If either an $X_1$ or $X_2$ occurs, the state is mapped into the space ${\rm Span}\{ \ket{01}, \ket{10} \}$, and a measurement of the stabilizer gives the output $-1$ (syndrome bit $1$).

A simpler circuit can be used for measuring stabilizers that perform a parity check. The circuit for performing the parity check in the 2-bit repetition code is shown in the below figure. 

```{figure} errorCorrectionStabMeasureCircuitParity.png
:alt: 
:class: bg-primary
:width: 600px
:align: center
:target: stab_measure_circuit_target

A circuit that checks the parity of two qubits and stores the result in an ancilla. $L_1$ and $L_2$ are used to label the two physical qubits used to create the single logical qubit. 
```

Firstly, the parity of two bits, $i_1, i_2 \in \{0,1\}$, is given by $i_1 \oplus i_2$. This will be zero if both bits are zero or both bits are one. If the bits differ, it will be one. 

Now, note that the action of a CNOT gate on some arbitrary computational basis state can be written as 
\begin{equation}
C_1X_2 \ket{i_1i_2} = \ket{i_1(i_2 \oplus i_1)}, ~ ~ i_1, i_2~\in~\{0,1\}.
\end{equation}
This works because a CNOT gate applies an $X$ gate to the second qubit if the first qubit is $i_1 = 1$. This $X$ gate will flip the second qubit, which can be done by adding $1$ to it. Hence, if $i_1 = 0$ nothing is added to the second qubit and it remains $i_2$. If $i_1=1$ then $1$ is added to $i_2$, flipping it. 

From here, consider that if it is not known if an error has occurred on an arbitrary qubit encoded into the code space, ${\rm Span}\{\ket{00}, \ket{11}\}$, the state can be written as
\begin{equation}
\alpha \ket{i_1 i_2} + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)}.
\end{equation}
The input into the circuit is then 
\begin{align*}
\big( \alpha \ket{i_1 i_2} + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)} \big) \otimes \ket{0}_A.
\end{align*}
The action of the first CNOT gate is then 
\begin{align*}
&C_2X_A \big( \alpha \ket{i_1 i_2} \otimes \ket{0}_A + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)} \otimes \ket{0}_A \big) \\
=&\alpha \ket{i_1 i_2} \otimes \ket{0 \oplus i_2}_A + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)} \otimes \ket{(i_2 \oplus 1)}_A \\
=& \alpha \ket{i_1 i_2} \otimes \ket{i_2} + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)} \otimes \ket{(i_2 \oplus 1)}_A,
\end{align*}
as $0 \oplus i_2 = i_2$. The action of the second CNOT gate is then 
\begin{align*}
&C_1X_A \big( \alpha \ket{i_1 i_2} \otimes \ket{i_2} + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)} \otimes \ket{(i_2 \oplus 1)}_A \big) \\
=&\alpha \ket{i_1 i_2} \otimes \ket{i_2 \oplus i_1} + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)} \otimes \ket{(i_2 \oplus 1) \oplus (i_1 \oplus 1)}_A \\
=& \alpha \ket{i_1 i_2} \otimes \ket{i_2 \oplus i_1} + \beta \ket{(i_1 \oplus 1)(i_2 \oplus 1)} \otimes \ket{i_2 \oplus i_1}_A,
\end{align*}
as $1 \oplus 1 = 0$. Hence, if $Z$ is measured on the computational basis then the parity is output with certainty. 
:::