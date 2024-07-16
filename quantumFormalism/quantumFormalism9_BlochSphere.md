---
title: The Bloch Sphere 
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
keywords: Bloch Vectors, Pure State, Mixed States, Sphere.  
abstract: The Bloch sphere representation of 2 dimensional quantum systems.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Definition 

The Bloch sphere is a geometrical way to represent both $d=2$ dimensional quantum systems (qubits) and the unitary dynamics of those $d=2$ dimensional systems.  

All possible qubit states, both mixed and pure, can be represented as a point on or inside of the unit sphere. Qubit dynamics can then be represented as rotations within this sphere. 

### Formalism 
Any qubit density operator $\rho \in \mathcal{H}^2$ has a Bloch sphere representation as 
\begin{equation}
\rho = \frac{1}{2} (\mathbb{I} + \bm{n} \cdot \bm{\sigma})
\end{equation}
where $\mathbb{I}$ is the $d=2$ dimensional idensity operator, $\bm{n} \in \mathbb{R}^{3}$ is the **Bloch vector**, and $\bm{\sigma}$ is a vector of Pauli operators, such that 
\begin{equation}
\bm{n} = \begin{pmatrix} n_x \\ n_y \\ n_z \end{pmatrix}, ~ ~ ~  \bm{\sigma} = \begin{pmatrix} X \\ Y \\ Z \end{pmatrix}.
\end{equation}
The elements of the Bloch vector can be found as 
\begin{align*}
n_x = \textrm{tr} \big[ \rho X \big], \\
n_y = \textrm{tr} \big[ \rho Y \big], \\
n_z = \textrm{tr} \big[ \rho Z \big]. \\
\end{align*}
Alternatively, in terms of spherical polar coordinates, the Bloch vector elements are given by 
\begin{align*}
n_x &= \vert n \vert \sin (\theta) \cos (\phi), \\
n_y &= \vert n \vert \sin (\theta) \sin (\phi), \\
n_z &= \vert n \vert \cos (\theta). \\
\end{align*}

### Properties 
1. $ \vert \bm{n} \vert = 1$ if and only if $ \rho $ is a pure state. If $ \vert \bm{n} \vert < 1$ then $ \rho $ is a mixed state. Hence, points on the surface of the sphere are pure states, whilst points in the interior of the sphere are mixed states. The small the norm of the Bloch vector, the more mixed a qubit state is. 
2. The qubit maximally mixed state, $ \rho = \frac{1}{2} \mathbb{I}$ has Bloch vector $\bm{n}_{mm} = (0,0,0)^{t}$. With $\vert \bm{n}_{mm} \vert = 0$ it can be seen that the qubit maximally mixed state sits at the centre of the unit circle. 

## Derivation 

## Orthogonality 

## Dynamics  