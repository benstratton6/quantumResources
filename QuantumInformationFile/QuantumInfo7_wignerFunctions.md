---
title: Wigner Functions
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
keywords:  Phase space, Wigner functions, continuous systems, discrete systems, Wooters. 
abstract: An overview of Winger functions for continuous and discrete quantum systems. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Introduction

[Quantum states](#quantum_state_page_target), both continuous and discrete, can be represented in terms of operators on a [Hilbert space](#hilbert_space_target). Alternatively, they can be represented as real valued functions - Wigner functions - on a phase space. Both methods contain the same information and the laws of quantum mechanics can be formulated in both paradigms. 

## Discrete Systems

In this section, the details of the [Wooters](https://doi.org/10.1016/0003-4916(87)90176-X) form of the discrete Wigner function is given.   

This is only valid for $d$-dimensional system where $d$ is a prime number. Systems that are not prime in dimension can be modelled in the phase space formalism by considering a composition of subsystems that are prime in dimension [💭](#prime_dimensions_quantum_info_glossary).  

### Phase Space

Consider a $d$-dimensional Hilbert space, $\mathcal{H}^d$, where $d$ is prime. This space has $d$ orthogonal states $\{ \ket{0}, \ket{1}, \ldots, \ket{d-1} \}$. 

The phase space associated to this discrete Hilbert space is a $d \times d$ grid of discrete points, each labeled by tuple $\bm{z} = (z_1, z_2)$, where $z_1, z_2 \in \mathbb{Z}_d = \{0, 1, \ldots, d-1 \}$. Hence, $\bm{z} = (z_1, z_2) \in \mathbb{Z}_d \times \mathbb{Z}_d$.  

A line in phase space is given by a set of points that satisfy $mz_1 + nz_2 = p$ where $m,n,p \in \mathbb{Z}_d$, with addition modulo $d$. Two lines are parallel if they differ only by $p$. There are $d(d+1)$ lines in the $\mathbb{Z}_d \times \mathbb{Z}_d$ phase space that can be grouped into $\hbox{d+1}$ sets of parallel lines. 

Each axis of the space is represented by an observable. If the horizontal axis is labelled by the observable $O_1$ then each vertical line is associated to a different eigenstate of $O_1$, with the eigenvalue labelling that horizontal coordinate. Likewise, if $O_2$ labels the vertical axis, each horizontal line is associated to a different eigenstate of $O_2$, with the eigenvalue labelling that vertical coordinate. 

### Phase-point Operators 

Each point in phase space is associated an Hermitian operator $A_{\bm{z}}$, giving a set of operators $\{ A_{\bm{z} }\}^{d^2}$. Each operators has the following properties: 
(conditions_on_phase_point_operators)=
1. $\textrm{tr} \big[ A_{\bm{z}} \big] = 1 ~ \forall ~ \bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d$.
2. $\textrm{tr} \big[ A_{\bm{z_i}} A_{\bm{z_j}} \big] = d \delta_{i,j} ~ \forall ~ \bm{z_i}, \bm{z_j} \in \mathbb{Z}_d \times \mathbb{Z}_d$.
3. Consider any set of $d$ parallel lines. Each of the $d$ lines in the set is described by $ \lambda_i $, which is the set of points that the line contains. For each line, the following operator can be defined: 
\begin{equation}
  P_\lambda = \frac{1}{d} \sum_{\bm{z} \in \lambda} A_{\bm{z}},
  \end{equation} 
which is the average of the phase-point operators along a given line. Let $ \{ P_{\lambda_i} \}_{i=1}^{d} $ be the set of operators for each line in a set of $d$ parallel lines. This set is mutually orthogonal and when summed over gives the identity. 

The set of phase-point operators is not unique. For example, any set that is unitarily equivalent to $\{ A_{\bm{z} }\}^{d^2}$ will also satisfy the above conditions. 

The set of phase-point operators now detailed are those that are typically used in the quantum computation literature. See https://dx.doi.org/10.1088/1367-2630/14/11/113011 and https://dx.doi.org/10.1088/1367-2630/16/1/013009 for more details.

The phase-point operators are constructed from the [Heisenberg-Weyl operators](#Weyl_operators_target) (see [Chp 4](https://cs.uwaterloo.ca/~watrous/TQI/) for more details). The Heisenberg-Weyl operators are built up from the so called shift and phase operators. In $\mathcal{H}^{d}$, the shift operator is defined as
\begin{equation}
X = \sum_{k \in \mathbb{Z}_d} \ket{k+1}\bra{k}, ~ ~ X \ket{j} = \ket{j + 1}, 
\end{equation}
where all addition is modulo $d$. The phase operator is defined as
\begin{equation}
Z = \sum_{k \in \mathbb{Z}_d} \omega^k \ket{k}\bra{k}, ~~ \omega = \exp \bigg( \frac{2 \pi i}{d} \bigg), ~ ~  Z \ket{j} = \omega^j \ket{j}.
\end{equation} 
From these, the Heisenberg-Weyl operators are defined as 
\begin{equation}

T_{\bm{z}=(z_1, z_2)} = \left\{
	\begin{array}{ll}
		i^{z_1 z_2} Z^{z_1}X^{z_2}, & (z_1, z_2) \in \mathbb{Z}_2 \times \mathbb{Z}_2,   \\
		\omega^{-(z_1 z_2)/2} Z^{z_1}X^{z_2}, & (z_1, z_2) \in \mathbb{Z}_d \times \mathbb{Z}_d, ~ d>2  \\
	\end{array}
\right.

\end{equation}
These Heisenberg-Weyl operators are the displacement operators in this discrete phase space. 

The phase point operators are then defined in terms of the Heisenberg-Weyl operators as 
\begin{equation}
A_{\bm{0}} = \frac{1}{d} \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d} T_{\bm{z}}, ~ ~ ~ A_{\bm{z}} = T_{\bm{z}}A_{\bm{0}} T_{\bm{z}}. 
\end{equation}

```{figure} quantumInfo_phaseSpaceImage.png
:alt: 
:class: bg-primary
:width: 800px
:align: center
<!-- :target: phase_space_winger_function_target -->

A graphical depiction of the phase space for the discrete Wigner function. 
```

### The Discrete Wigner Function 

Let $\rho \in \mathcal{H}^{d}$. Given [condition 2](#conditions_on_phase_point_operators) stated above in the list of properties of phase-point operators, the set of phase-point operators form a complete basis for the set of $d \times d$ Hermitian matrices. The discrete Wigner function, denoted $W^{\rho}_{\bm{z}}$ at the point $\bm{z}$ for the state $ \rho $, is then defined as
\begin{equation}
\rho = \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d }   W^{\rho}_{\bm{z}} A_{\bm{z}}, 
\end{equation}
such that 
\begin{equation}
W^{\rho}_{\bm{z}} = \frac{1}{d} \textrm{tr} \big[ \rho A_{\bm{z}} \big].
\end{equation}

The discrete Wigner function then satisfies the following properties
(discrete_winger_function_conditions)=
1. $ \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d } W^{\rho}_{\bm{z}} = 1$. 
2. Let $\rho, \rho' \in \mathcal{H}^d$ have Wigner functions $W^{\rho}$ and $W^{\rho'}$ respectively, then 
\begin{equation}
\textrm{tr} \big[ \rho \rho' \big] = d \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d } W^{\rho}_{\bm{z}} W^{\rho'}_{\bm{z}}.
\end{equation}
3. The phase space can be foliated into a set of $d$ parallel lines. For each line, given by $ \lambda $, the sum over the Wigner functions for the points in $ \lambda $, $p_{\lambda} = \sum_{\lambda} W^{\rho}_\lambda$, describes the probability of a measurement associated to that foliation. The eigenstate associated to this measurement is that of the projection operator, given in [condition 3](#conditions_on_phase_point_operators), for the given foliation. 

Note, the Wigner function can be negative, meaning it cannot be directly interpreted as a probability distribution. As with the state vector or density operator, it is instead an object from which probabilities of measurement outcomes can be found. 

There are $d+1$ different foliations of the phase space into sets of $d$ parallel lines. As given in [condition 3](#discrete_winger_function_conditions) above, a measurement can be associated to each set of parallel lines. The eigenbasis of the measurements associated to each set have [mutually unbiased basis](#https://en.wikipedia.org/wiki/Mutually_unbiased_bases). 


### Composite Systems 

The above was all for systems that are $d$-dimensional where $d$ is a prime number. System that have a non-prime dimension can be build up out of systems that do have prime dimensions, such as $d=2$ systems. 

Firstly, one factorises $d$ into prime numbers: $d = d_1, d_2, \ldots, d_n$, such that $d_i$ is prime for all $i \in \{ 1, n \}$. To each $d_i$ a phase space can be associated, that is an array of points $\bm{z}_i \in \mathbb{Z}_{d_i} \times \mathbb{Z}_{d_i}$. The total phase space is taken to be the [Cartesian product](https://en.wikipedia.org/wiki/Cartesian_product) of these phase spaces. Given two sets $A$ and $B$, the Cartesian product is 
\begin{equation}
A \oplus B = \{ (a,b): a \in A, b \in B \}.
\end{equation}
Therefore, a point in the total phase space of a composite system is given by an ordered tuple of points from the different subsystems,
\begin{equation}
\bm{z} = (\bm{z}_1, \bm{z}_2, \ldots, \bm{z}_n).
\end{equation}  
Note, the different subsystems can be different dimensions. 

In composite systems, lines becomes slices. Given a set of lines, one from each subsystem, a slice is the set of points from all subsystems that are contained in the set of lines. 

Phase-point operators can be found for these composite systems by taking the tensor product of the phase-point operators for the different subsystems,
\begin{equation}
A_{\bm{z}} = A_{\bm{z}_1} \otimes A_{\bm{z}_2} \otimes \ldots \otimes A_{\bm{z}_n}.
\end{equation}
All the [properties of phase-point operators](#conditions_on_phase_point_operators) given above still apply for the phase point operators of composite systems but with notion of a line replaced by a slice. 

The Wigner function for composite systems is calculated in the same way as for non-composite systems. 

### Further Properties

:::{dropdown} Definitions


The follow definitions are used in the below properties of the discrete Winger functions. 

1. Clifford operators, $C$, are the set of unitaries that map the Heisenberg-Weyl operators to themselves up to a phase. Specifically, a unitary $U \in C$ if and only if 
\begin{equation}
\forall \bm{z} ~\exist ~\bm{z'}, \phi ~ ~ \textrm{such that} ~ ~ U T_{\bm{z}} U^{\dagger} = e^{i \phi} T_{\bm{z'}}.
\end{equation}
2. The set of stabliser states is the convex combination of states that can be reached from $\ket{0}$ by the Clifford operators,
\begin{equation}
\textrm{STAB} = \textrm{conv} \{ U \ket{0} : U \in C \}.
\end{equation} 

See https://dx.doi.org/10.1088/1367-2630/14/11/113011 and https://dx.doi.org/10.1088/1367-2630/16/1/013009 for more details.

:::

1. Discrete Hudson's Theorem (prime dimensions): A pure state, $\ket{S}$, is a stabliser state, $\ket{S} \in \textrm{STAB}$, if and only if it has positve Wigner representation 
\begin{equation}
W^{\ket{S}}_{\bm{z}} \geq 0 ~ \forall ~\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d.
\end{equation}
2. Clifford operators act as permutations of the phase-space
\begin{equation}
W_{\bm{z}}^{U \rho U^{\dagger}} = W_{\bm{z'}}^{\rho}, ~ ~ U \in C.
\end{equation}
Although, only the [symplectic](https://en.wikipedia.org/wiki/Symplectic_matrix) permutations of phase space correspond to clifford operators. 

3. As discussed above, the phase-point operators are a basis for all $d \times d$ Hermitian matrices. Hence, the trace of any Hermitain matrix can be found by summing over it's Wigner function for all point in phase space, 
\begin{align*}
B &= \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d} W^{B}_{\bm{z}} A_{\bm{z}}, \\
\textrm{tr} \big[ B \big] &= \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d} W^{B}_{\bm{z}},
\end{align*}
where the fact that $\textrm{tr}\big[ A_{\bm{z}} \big] = 1 ~\forall~\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d$ has been used. 

## Phase Space for POVMs and Channels

## Further Reading

 1. For Wigner Functions in Discrete Spaces - [A Wigner-function formulation of finite-state quantum mechanics](https://doi.org/10.1016/0003-4916(87)90176-X)
 2. Review Article on quantum mechanics in phase space - [Overview of the Phase Space Formulation of Quantum Mechanics with Application to Quantum Technologies](https://doi.org/10.1002/qute.202100016)

