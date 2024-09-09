---
title: Commutators
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
keywords: Operators, Commute, Shared Basis.  
abstract: An overview of commutators and their physical implications in quantum mechanics. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

(commutators_whole_page_target)=

## Definition  

Let $A, B$ be two operators. The commutator of $A$ and $B$ is given by 
\begin{equation}
[A,B] = AB - BA. 
\end{equation}
This means multiply the operator $A$ on the left by $B$, and then taking off the operator $B$ multiplied on the left by $A$. 

When considering the matrix decomposition of these operators, $A'$ and $B'$, this relation can be seen as matrices for which their ordered multiplication is not equal: $A'B' \neq B'A'$.  

## Commutator Identities    

Here are some common commutator identities that are useful. 

Let $A,B,C$ be some operators and $\mathbb{I}$ be the identity operator. 

1. $[A,A] = 0$.
2. $[A, \mathbb{I}] = 0$.
3. $[A,B]=-[B,A]$.
4. $[A,BC] = [A,B]C + B[A,C]$.
5. $[AB,C] = A[B,C] + [A,C]B$. 

## Mathematical Implications

When two [observables](#obersvables_definition_observable_page_target) $A$ and $B$ commute, $[A,B] = 0$, they share a common eigenbasis. 

:::{dropdown} Proof

Here, the non-degenerate case is considered. See [here](https://en.wikipedia.org/wiki/Complete_set_of_commuting_observables#cite_note-1) for the degenerate case. 

Let $A = \sum_{j} j \ket{j}\bra{j}$, such that $A \ket{j} = j \ket{j}$. 

Consider the following: 
\begin{align*}
AB \ket{j} &= A \big( B \ket{j} \big). \\
BA \ket{j} &= B \big( A \ket{j} \big) = B \big( j \ket{j} \big) = j \big( B \ket{j} \big),
\end{align*}
where the $j$ can be moved past the operator B in the final line as $j$ is just some number. Given $AB=BA$, we can then write 
\begin{equation}
A \big( B \ket{j} \big) = j \big( B \ket{j} \big),
\end{equation}
meaning that $B\ket{j}$ is an eigenvector of $A$ with eigenvalue $j$. Hence, $B\ket{j}$ is proportional to $\ket{j}$ - it is a vector that points in the same direction as $\ket{j}$ but does not necessarily have the same length. One can therefore write 
\begin{equation}
B \ket{j} = b_j \ket{j},
\end{equation}
where $b_j$ is some number, meaning that $\ket{j}$ is also an eigenvector of $B$. This can be repeated for the whole basis, such that it is possible to write $B = \sum_j b_j \ket{j} \bra{j}$.

:::

### Degenerate Operators

If $A$ and $B$ are [non-degenerate](#degenerate_definition_target_eigenvalues_page) operators then the shared eigenbasis is unique. 

That is, each non-degenerate eigenvector of $A$ is also an eigenvector of $B$. 

### Non-degenerate Operators

If $A$ is degenerate then in the degenerate sub-space there are an infinite number of vectors that are eigenvectors of $A$ - namely, any linear combination of eigenvectors in the degenerate eigenspace is also an eigenvector $A$. A common eigenbasis can still be found but it is in general not unique. 

For each degenerate eigenvalue $ \alpha $ of $A$, of [multiplicity](#multiplicity_quantum_info_glossary) $n$, one can find a set of $n$ eigenvectors, $\{ \ket{\phi_m} \}_{m=0}^{n-1}$, such that 
\begin{align*}
A \ket{\phi_m} &= \alpha \ket{\phi_m} ~\forall~m~\in~[0,n-1], \\
B \ket{\phi_m} &= \lambda_m \ket{\phi_m}~\forall~m~\in~[0,n-1].
\end{align*}

Hence, each $\ket{\phi_m}$ is an eigenvector of both $A$ and $B$, but not all eigenvectors of $A$ corresponding to the degenerate eigenvalue $ \alpha $ are eigenvectors of $B$. 

Nothing can be said about the eigenvalues, $ \lambda_m $, from this theory. 

## Physical Implication 

The fact that there exists observables for which $[A,B] \neq 0$ is the origin of much that is interesting about quantum mechanics. Physically, it means that measuring $A$ and then $B$ on a state $\ket{\psi}$ will give a different outcome to measuring $B$ and then $A$ on $\ket{\psi}$. This is due to measurement physically changing the underlying state. 

The consequence of this is that it is not possible to simultaneously measure the observables $A$ and $B$ if they do not commute. For example, there exists sets of states and measurements for which a measurement of $A$ means one is completely uncertain about what measurement outcome they would get if they were to then measure $B$. In this case, measuring $A$ (and hence knowing it with certainty) makes one maximally uncertain about what measurement outcome they would get when measuring $B$.  

To see why a shared eigenbasis allows simultaneous measurement, consider a state, $\ket{\psi}$, upon which the observable $A$ is measured where $[A,B] = 0$. If $A=\sum j \ket{j}\bra{j}$, then the measurement outcome will be some eigenvalue $k$ and the post measurement state will be the associated eigenvector $\ket{k}$. Considering now that the observable $B$ is then measured on the same system. As $A$ and $B$ share a common eigenbasis, $\ket{k}$ is also an eigenvector of $B$ and hence the measurement outcome will be $b_k$, where $B\ket{k}=b_k\ket{k}$, with certainty. Therefore, if one knows the measurement outcome from measuring $A$, they know for certain what the measurement outcome from measuring $B$ will be. Moreover, if they were to measure $A$ again, they would again get $k$ with certainty. Hence, they can know both measurement outcomes simultaneously with certainty. 

If the observables do not commute, $[A,B] \neq 0$, they do not share a common eigenbasis. After measuring $A$, the state will be in an eigenvector of the observable $A$. After measuring $B$, the state will be in an eigenvector of the observable $B$. Each measurement projects the state onto a different basis, with the output state being probabilistic each time. cycling through measurements of $A, B, A, B \ldots$ could therefore give different measurement outcomes each time the same observable is measured. 
