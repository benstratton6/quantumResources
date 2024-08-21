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
abstract: An overview of Winger functions for continuous and discrete quantum systems. Particular detail is given to the discrete case. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Introduction

[Quantum states](#quantum_state_page_target), both continuous and discrete, can be represented in terms of operators on a [Hilbert space](#hilbert_space_target). Alternatively, they can be represented as real valued functions - Wigner functions - on a phase space. Both methods contain the same information and the laws of quantum mechanics can be formulated in both paradigms. 

This article will primarily focus on the discrete Wigner function. However, given its was initially form for continuous systems they will be briefly covered. 

## Continuous Systems

In this section, Wigners orginal formulation of quantum mechanics in phase space is briefly covered. 

Let $\rho \in \mathcal{H}^d$ be the density operator of a particle that is able to move in one dimension. The Wigner function is defined as 
\begin{equation}
W^{\rho}(q, p) = \frac{1}{\pi \hbar} \int \bra{q-x} \rho \ket{q+x} e^{\frac{2ipx}{h}} dx,
\end{equation}
where $ q $ and $ p $ are the position and momentum operators (they could also be [quadratures](https://en.wikipedia.org/wiki/Optical_phase_space) when considered quantum optics). 

Here, we will only consider the Wigner function for position and momentum, see https://doi.org/10.1002/qute.202100016 for details on the Wigner function for arbitrary operators. 

**Properties of the Continuous Winger Function:** 
(winger_function_proerties_continious)=
::::{tab-set}
:::{tab-item} Normalisation
:sync: tab1

The Wigner function is normalised, 
\begin{equation}
\int \int W^{\rho}(p, q) dq ~ dp = 1.
\end{equation}

:::
:::{tab-item} Inner Product 
:sync: tab2

Let $\rho, \rho' \in \mathcal{H}^d$ have Wigner functions $W^{\rho}(q,p)$ and $W^{\rho'}(q,p)$ respectively, then 
\begin{equation}
\textrm{tr}\big[ \rho \rho' \big] = \int \int W^{\rho}(q, p) W^{\rho'}(q, p) dq ~ dp.
\end{equation}

:::
:::{tab-item} Observables
:sync: tab3

Let $O=a p + b q$ be an observable, where $a, b \in \mathbb{R}$, then 
\begin{equation}
P(c_1 \leq O \leq c_2) = \int_{c_1}^{c_2} \int_{c_1}^{c_2} W^{\rho}(p, q) dq ~ dp,
\end{equation}
where $c_1, c_2 \in \mathbb{R}$, and $P(\cdot)$ means the probability of getting the measurement outcome $(\cdot)$ if one measures $O$ on $ \rho $.

:::
:::{tab-item} Marginals 
:sync: tab4

The Wigner function can be used to find the marginals of the distribution as 
\begin{align*}
\int W^{\rho}(q,p) dp &= \bra{x} \rho \ket{x}, \\
\int W^{\rho}(q,p) dq &= \bra{p} \rho \ket{p}.
\end{align*}

::::

<!-- **Properties** 
(winger_function_proerties_continious)=
1. The Wigner function is normalised, 
\begin{equation}
\int \int W^{\rho}(p, q) dq ~ dp = 1.
\end{equation}
2. Let $\rho, \rho' \in \mathcal{H}^d$ have Wigner functions $W^{\rho}(q,p)$ and $W^{\rho'}(q,p)$ respectively, then 
\begin{equation}
\textrm{tr}\big[ \rho \rho' \big] = \int \int W^{\rho}(q, p) W^{\rho'}(q, p) dq ~ dp.
\end{equation}
3. Let $O=a p + b q$ be an observable, where $a, b \in \mathbb{R}$, then 
\begin{equation}
P(c_1 \leq O \leq c_2) = \int_{c_1}^{c_2} \int_{c_1}^{c_2} W^{\rho}(p, q) dq ~ dp,
\end{equation}
where $c_1, c_2 \in \mathbb{R}$, and $P(\cdot)$ means the probability of getting the measurement outcome $(\cdot)$ if one measures $O$ on $ \rho $.  
4. The Wigner function can be used to find the marginals of the distribution as 
\begin{align*}
\int W^{\rho}(q,p) dp &= \bra{x} \rho \ket{x}, \\
\int W^{\rho}(q,p) dq &= \bra{p} \rho \ket{p}.
\end{align*} -->


**Phase Space:**

The phase space on which the Wigner function is defined is $\mathbb{R}^2$. This is due to position and momentum being continuous variables and hence they are able to be any real value, $(q,p), \in \mathbb{R}^2$.  

**Phase Point Operators:**

The Wigner function for a state can be calculated using the so-called phase-point operators. These are a set of Hermitian operators, $\{A(q,p)\}$. There exists one phase-point operator for each point in phase space. 

The phase-point operators are defined such that 
\begin{equation}
\rho = \int \int W^{\rho}(q,p) A(q,p) dq~dp. \label{test}
\end{equation}

The Wigner function at a point $(q,p)$ can be found from the phase-point operators as 
\begin{equation}
W^{\rho}(q,p) = \frac{1}{2 \pi \hbar} \textrm{tr} \big[ \rho A(q,p) \big].
\end{equation}

The phase point operators have the following properties:
1. $\textrm{tr}\big[ A(q,p) \big] = 1~\forall~(q,p) \in \mathbb{R}^2$. 
2. $\textrm{tr}\big[ A(q,p) A(q',p') \big] = 2 \pi \hbar \delta(q - q') \delta(p-p') ~\forall~(q,p), (q',p') \in \mathbb{R}^2$
3. Given an operator $O=a p + b q$, consider the strip of phase space such that $c_1 \leq O \leq c_2$. The follow operator is a projection onto the eigenstates of $O$ with eigenvalues between $c_1$ and $c_2$, 
\begin{equation}
P = \int_{c_1}^{c_2} \int_{c_1}^{c_2} A(q,p) dq~dp.
\end{equation}

If the phase-point operators obey these properties, then the Winger functions obeys the conditions given [above](#winger_function_proerties_continious). 

Note, when considering the Wigner function for general operators, the phase point operators can be defined in terms of the action of a displacement operator on a fixed initial phase-point operator (as will be seen in the discrete case below). See https://doi.org/10.1002/qute.202100016 detail of this.

**Uniqueness**

The Wigner function is not the unique function that is able to represent quantum systems. Each of the different formulations put forward have different merits, and hence can be useful in different situations. However, the Wigner function is the mostly commonly used in the literature as it a) has the correct marginals, and b) it is the function for which the phase-point operators can be used to both decompose the state with coefficients of the Wigner function, and to calculate the Wigner function as the trace of the product of the phase-point operators and $ \rho $. Other formulations require different operators for these two operations. Again, see https://doi.org/10.1002/qute.202100016 for more details on this. 

## Discrete Systems

In this section, the details of the [Wooters](https://doi.org/10.1016/0003-4916(87)90176-X) form of the discrete Wigner function is given.   

This is only valid for $d$-dimensional system where $d$ is a prime number. Systems that are not prime in dimension can be modelled in the phase space formalism by considering a composition of subsystems that are prime in dimension [💭](#prime_dimensions_quantum_info_glossary).  

**Phase Space:**

Consider a $d$-dimensional Hilbert space, $\mathcal{H}^d$, where $d$ is prime. This space has $d$ orthogonal states $\{ \ket{0}, \ket{1}, \ldots, \ket{d-1} \}$. 

The phase space associated to this discrete Hilbert space is a $d \times d$ grid of discrete points, each labeled by tuple $\bm{z} = (z_1, z_2)$, where $z_1, z_2 \in \mathbb{Z}_d = \{0, 1, \ldots, d-1 \}$. Hence, $\bm{z} = (z_1, z_2) \in \mathbb{Z}_d \times \mathbb{Z}_d$.  

A line in phase space is given by a set of points that satisfy $mz_1 + nz_2 = p$ where $m,n,p \in \mathbb{Z}_d$, with addition modulo $d$. Two lines are parallel if they differ only by $p$. There are $d(d+1)$ lines in the $\mathbb{Z}_d \times \mathbb{Z}_d$ phase space that can be grouped into $\hbox{d+1}$ sets of parallel lines. 

Each axis of the space is represented by an observable. If the horizontal axis is labelled by the observable $O_1$ then each vertical line is associated to a different eigenstate of $O_1$, with the eigenvalue labelling that horizontal coordinate. Likewise, if $O_2$ labels the vertical axis, each horizontal line is associated to a different eigenstate of $O_2$, with the eigenvalue labelling that vertical coordinate. 

**Phase-point Operators:**

Each point in phase space is associated an Hermitian operator $A_{\bm{z}}$, giving a set of operators $\{ A_{\bm{z} }\}^{d^2}$, one for each point in phase space. Each operator obeys the following properties: 
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

**Additional Phase-point Operator Properties**
1. $A_{\bm{z}}^{\dagger} = A_{\bm{z}}$
    - They are Hermitian. 
2. $\frac{1}{d}\sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d} A_{\bm{z}} = \mathbb{I}$.
    - They sum to the identity. 
3. $ \{ A_{\bm{z}} \} = \{ A_{\bm{z}}^{t} \}$
    - Taking the transpose off all elements of the set gives back the set.

```{figure} quantumInfo_phaseSpaceImage.png
:alt: 
:class: bg-primary
:width: 800px
:align: center
<!-- :target: phase_space_winger_function_target -->

A graphical depiction of the phase space for the discrete Wigner function. 
```

**The Discrete Wigner Function:**

Let $\rho \in \mathcal{H}^{d}$. Given [condition 2](#conditions_on_phase_point_operators) stated above in the list of properties of phase-point operators, the set of phase-point operators form a complete basis for the set of $d \times d$ Hermitian matrices. The discrete Wigner function, denoted $W^{\rho}(\bm{z})$ at the point $\bm{z}$ for the state $ \rho $, is then defined as
\begin{equation}
\rho = \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d }   W^{\rho}(\bm{z}) A_{\bm{z}}, 
\end{equation}
such that 
\begin{equation}
W^{\rho}(\bm{z}) = \frac{1}{d} \textrm{tr} \big[ \rho A_{\bm{z}} \big].
\end{equation}

The discrete Wigner function then satisfies the following properties
(discrete_winger_function_conditions)=
1. $ \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d } W^{\rho}(\bm{z}) = 1$. 
2. Let $\rho, \rho' \in \mathcal{H}^d$ have Wigner functions $W^{\rho}(\bm{z})$ and $W^{\rho'}(\bm{z})$ respectively, then 
\begin{equation}
\textrm{tr} \big[ \rho \rho' \big] = d \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d } W^{\rho}(\bm{z}) W^{\rho'}(\bm{z}).
\end{equation}
3. The phase space can be foliated into a set of $d$ parallel lines. For each line, given by $ \lambda $, the sum over the Wigner functions for the points in $ \lambda $, $p_{\lambda} = \sum_{\lambda} W^{\rho}_\lambda(\bm{z})$, describes the probability of a measurement associated to that foliation. The eigenstate associated to this measurement is that of the projection operator, given in [condition 3](#conditions_on_phase_point_operators), for the given foliation. 

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
W^{\ket{S}}(\bm{z}) \geq 0 ~ \forall ~\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d.
\end{equation}
2. Clifford operators act as permutations of the phase-space
\begin{equation}
W^{U \rho U^{\dagger}}(\bm{z}) = W^{\rho}(\bm{z}), ~ ~ U \in C.
\end{equation}
Although, only the [symplectic](https://en.wikipedia.org/wiki/Symplectic_matrix) permutations of phase space correspond to clifford operators. 

3. As discussed above, the phase-point operators are a basis for all $d \times d$ Hermitian matrices. Hence, the trace of any Hermitain matrix can be found by summing over it's Wigner function for all point in phase space, 
\begin{align*}
B &= \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d} W^{B}(\bm{z}) A_{\bm{z}}, \\
\textrm{tr} \big[ B \big] &= \sum_{\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d} W^{B}(\bm{z}),
\end{align*}
where the fact that $\textrm{tr}\big[ A_{\bm{z}} \big] = 1 ~\forall~\bm{z} \in \mathbb{Z}_d \times \mathbb{Z}_d$ has been used. 

## Phase Space for General Hermitian Operators, POVMs and Channel

See https://doi.org/10.1088/1367-2630/ab451d more full details on these definitions. 

**General Hermitian Operators**

Let $X \in \mathcal{H}^d$ be a Hermitian operator, such that $X^\dagger = X$.  

The discrete Winger function at a point $\bm{z}$ of the operator $X$ is given by
\begin{equation}
W(X) = \frac{1}{d}~\textrm{tr}\big[XA_{\bm{z}}\big].
\end{equation}

**POVMS**

Let $\{ E_u \}$ be a POVM, so that $E_u \geq 0~\forall~u$ and $\sum_u E_u = \mathbb{I}$. 

The discrete Winger function at a point $\bm{z}$ of an operator $E_u$ is given by 
\begin{equation}
W(E_u \vert \bm{z}) = \textrm{tr}\big[EA_{\bm{z}}\big],
\end{equation}
where 
\begin{equation}
\sum_u W(E_u \vert \bm{z}) = 1.
\end{equation}

**Channels** 

Let $\mathcal{N}: \mathcal{H}_A \rightarrow \mathcal{H}_B$ be a [quantum channel](#quantum_channel_page_target). 

The discrete Winger function at a point $\bm{z}$ of the operator $X$ is given by
\begin{align*}
W_{\mathcal{N}}(\bm{z} \vert \bm{y}) &= \frac{1}{d_b} \textrm{tr} \big[ ((A_A^{\bm{y}})^{t} \otimes A_B^{\bm{z}}) \mathcal{J}^{\mathcal{N}}_{AB} \big], \\
&= \frac{1}{d_b} \textrm{tr} \big[ A^{\bm{z}}_B \mathcal{N}(A^{\bm{y}}_A) \big],
\end{align*}
where $\mathcal{J}^{\mathcal{N}}_{AB}$ is the [Choi-state](choi_state_target_quantum_channels_page) of $\mathcal{N}$ and $A_A^{\bm{u}}$ is the phase point operator in the $A$ space at the point $\bm{u}$. It is the case that 
\begin{equation}
\sum_{\bm{z}} W_{\mathcal{N}}(\bm{z} \vert \bm{y}) = 1 ~\forall ~ \bm{y}.
\end{equation}
## Further Reading

 1. For Wigner Functions in Discrete Spaces - [A Wigner-function formulation of finite-state quantum mechanics](https://doi.org/10.1016/0003-4916(87)90176-X)
 2. Review Article on quantum mechanics in phase space - [Overview of the Phase Space Formulation of Quantum Mechanics with Application to Quantum Technologies](https://doi.org/10.1002/qute.202100016)
 3. Review Article on general quasi-probability representations of quantum theory - [Quasi-probability representations of quantum theory with applications to quantum information science](https://doi.org/10.1088/0034-4885/74/11/116001)

