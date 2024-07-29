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

[Quantum states](#quantum_state_page_target), both continuous and discrete, can be represented in terms of operators on [Hilbert space](#hilbert_space_target). Alternatively, they can be represented as real valued functions - Wigner functions - on a phase space. Both methods contain the same information and the laws of quantum mechanics can be formulated in both of these paradigms. 

## Discrete Systems

In this section the details of the [Wooters](https://doi.org/10.1016/0003-4916(87)90176-X) form of the discrete Wigner function is given.   

This is only valid for $d$-dimensional system where $d$ is a prime number. Systems that are not prime in dimension can be modelled in the phase space formalism by considering a composition of subsystems that are prime in dimension [💭](#prime_dimensions_quantum_info_glossary).  

### Phase Space

Consider a $d$-dimensional Hilbert space, $\mathcal{H}^d$, where $d$ is prime. This space has $d$ orthogonal states $\{ \ket{0}, \ket{1}, \ldots, \ket{d-1} \}$. 

The phase space associated to this discrete Hilbert space is a $d \times d$ grid of discrete points, each labeled by $\bm{z} = (z_1, z_2)$ where $z_1, z_2 \in \mathbb{Z}_d = \{0, 1, \ldots, d-1 \}$. Hence, $\bm{z} = (z_1, z_2) \in \mathbb{Z}_d \times \mathbb{Z}_d$.

A line in this phase space is given by a set of points that satisfy $mz_1 + nz_2 = p$ where $m,n,p \in \mathbb{Z}_d$. Two lines are then parallel if they differ only by $p$. There are $d(d+1)$ lines in the $d \times d$ phase space that can be grouped into $d+1$ sets of parallel lines. 

Each axis of the space is represented by an operator. If the horizontal axis is labelled by the operator $O_1$ then each vertical line is associated to a different eigenstate of $O_1$, with the eigenvalue label that horizontal coordinate. Likewise, if $O_2$ labels the vertical axis, each horizontal line is associated to a different eigenstate of $O_2$, with the eigenvalue label that vertical coordinate. 

### Phase-point Operators 

Each point in phase space is associated an Hermitian operator $A_{\bm{z}}$ with the following properties 

1. $\textrm{tr} \big[ A_{\bm{z}} \big] = 1, \forall ~ \bm{z}$
2. $\textrm{tr} \big[ A_{\bm{z_i}} A_{\bm{z_j}} \big] = d \delta_{i,j}, \forall ~ \bm{z_i}, \bm{z_j}$
3. Consider any set of $N$ parallel lines. Each of the $N$ lines in the set is described by $ \lambda_i $, which is the set of points that the line contains. For each line, the following operator can be defined: 
\begin{equation}
  P_\lambda = \frac{1}{d} \sum_{\bm{z} \in \lambda} A_{\bm{z}},
  \end{equation}
  which is the average of the phase-point operators along a given line. Let $ \{ P_{\lambda_i} \}_{i=1}^{d} $ be the set of operators for each line in a set of $N$ parallel lines. This set is mutually orthogonal and when summed over gives the identity. 

The set of phase-point operators is not unique - any set that is unitarily equivalent to set with the above properties will work, for example. The following set of phase point operator are those that are typically used in the literature [(https://dx.doi.org/10.1088/1367-2630/14/11/113011, https://dx.doi.org/10.1088/1367-2630/16/1/013009)] on discrete Wigner functions for quantum computation.

The phase-point operators are constructed from the [Heisenberg-Weyl operators](#Weyl_operators_target) (see [here](https://cs.uwaterloo.ca/~watrous/TQI/), Chp 4 for more details on these). In $\mathcal{H}^{d}$, the so called shift operators is defined as
\begin{equation}
X = \sum_{k \in \mathbb{Z}_d} \ket{k+1}\bra{k}, ~ ~ X \ket{j} = \ket{j + 1}, 
\end{equation}
where all addition is modulo $d$. The so called phase operator are defined as
\begin{equation}
Z = \sum_{k \in \mathbb{Z}_d} \omega^k \ket{k}\bra{k}, ~ ~ Z \ket{j} = \omega^j \ket{j},
\end{equation} 
where 
\begin{equation}
\omega = \exp \bigg( \frac{2 \pi i}{d} \bigg).
\end{equation}
The Heisenberg-Weyl operators are then defined as 
\begin{equation}

W_{\bm{z}} = \left\{
	\begin{array}{ll}
		i^{z_1 z_2} Z^{z_1}X^{z_2}, & (z_1, z_2) \in \mathbb{Z}_2 \times \mathbb{Z}_2,   \\
		\omega^{-(z_1 z_2)/2} Z^{z_1}X^{z_2}, & (z_1, z_2) \in \mathbb{Z}_d \times \mathbb{Z}_d, ~ d>2  \\
	\end{array}
\right.

\end{equation}
 ## Further Reading

 1. For Wigner Functions in Discrete Spaces - [A Wigner-function formulation of finite-state quantum mechanics](https://doi.org/10.1016/0003-4916(87)90176-X)
 2. Review Article on Phase space - [Overview of the Phase Space Formulation of Quantum Mechanics with Application to Quantum Technologies](https://doi.org/10.1002/qute.202100016)

