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

## Stabilizer Codes

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

     