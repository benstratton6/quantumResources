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

All possible qubit states, both pure and mixed, can be represented as a point on or inside of a unit sphere. Qubit dynamics can then be represented as rotations on the unit sphere. 

## States

Any qubit density operator $\rho \in \mathcal{H}^2$ has a Bloch sphere representation as 
\begin{equation}
\rho = \frac{1}{2} (\mathbb{I} + \bm{n} \cdot \bm{\sigma})
\end{equation}
where $\mathbb{I}$ is the $d=2$ dimensional identity operator, $\bm{n} \in \mathbb{R}^{3}$ is the **Bloch vector**, and $\bm{\sigma}$ is a vector of [Pauli operators](https://en.wikipedia.org/wiki/Pauli_matrices), such that 
\begin{equation}
\bm{n} = \begin{pmatrix} n_x \\ n_y \\ n_z \end{pmatrix}, ~ ~ ~  \bm{\sigma} = \begin{pmatrix} X \\ Y \\ Z \end{pmatrix},
\end{equation}
where 
\begin{equation}

X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, ~~ Y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, ~ ~ Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}.

\end{equation}
The elements of the Bloch vector can be found as 
\begin{align*}
n_x = \textrm{tr} \big[ \rho X \big], \\
n_y = \textrm{tr} \big[ \rho Y \big], \\
n_z = \textrm{tr} \big[ \rho Z \big]. \\
\end{align*}
The $\frac{1}{2} \mathbb{I}$ terms fixes the normalisation, such that $\textrm{tr}\big[ \rho \big] = 1$.

Alternatively, in terms of [spherical polar coordinates](https://en.wikipedia.org/wiki/Spherical_coordinate_system), the Bloch vector elements are given by 
\begin{align*}
n_x &= \vert n \vert \sin (\theta) \cos (\phi), \\
n_y &= \vert n \vert \sin (\theta) \sin (\phi), \\
n_z &= \vert n \vert \cos (\theta), \\
\end{align*}
where the norm of the Bloch vector is the taken as the radius. Each set of three coordinates $( \theta, \phi, \vert n \vert)$ represent a uniquely qubit state. 

### Properties 
1. $ \vert \bm{n} \vert = 1$ if and only if $ \rho $ is a pure state. If $ \vert \bm{n} \vert < 1$ then $ \rho $ is a mixed state. Hence, points on the surface of the sphere are pure states, whilst points in the interior of the sphere are mixed states. The smaller the norm of the Bloch vector, the more mixed a qubit state is. 
2. The qubit maximally mixed state, $ \rho = \frac{1}{2} \mathbb{I}$, has Bloch vector $\bm{n}_{mm} = (0,0,0)^{t}$. With $\vert \bm{n}_{mm} \vert = 0$ it can be seen that the qubit maximally mixed state sits at the centre of the unit circle. 
 

:::{dropdown} Derivation of Bloch Sphere


Initially, pure qubit states will be considered. 

**Firstly, a general form for pure qubit states is found**. A pure qubit state can be written with respect to the standard basis as 
\begin{equation}
\ket{\psi} = \alpha \ket{0} + \beta \ket{1},
\end{equation}
where $\alpha, \beta ~\in~\mathbb{C}^{1}$. By writing the complex numbers in polar coordinates, the qubit state can equivalently be written as 
\begin{equation}
\ket{\psi} = r_\alpha e^{i \phi_\alpha} \ket{0} + r_\beta e^{i \phi_\beta} \ket{1}.
\end{equation}
From here, it looks as if four real numbers are needed to specify a general qubit state: $r_\alpha, \phi_\alpha, r_\beta, \phi_\beta$. 

However, all quantum states can be multiplied by a global phase without it effecting the measurement outcomes (the density operator, which holds all information about the possible measurement outcomes, of $\ket{\psi}$ and $e^{i \omega}\ket{\psi}$ are the same). Hence, $ \ket{\psi} $ can be multiplied by $e^{-i \phi_\alpha}$ without loss of generality, giving 
\begin{equation}
\ket{\psi} = r_\alpha \ket{0} + r_\beta e^{i (\phi_\beta - \phi_\alpha)} \ket{1}.
\end{equation}
It now looks as if three real numbers are needed to specify a general qubit state: $r_\alpha, r_\beta, (\phi_\beta-\phi_\alpha)$. 

Although, valid quantum states are also [normalised](#normalised_quantum_states_target), 
\begin{equation}
 \braket{\psi|\psi} = 1,
\end{equation}
giving 
\begin{equation}
r_\alpha^2 + r_\beta^2 = 1,
\end{equation}
which looks like the equation of a unit circle in 2d plane. Hence, we can let $r_\alpha = \cos(\theta), r_\beta = \sin(\theta)$ and $ \phi = \phi_\beta - \phi_\alpha$, giving 
\begin{equation}
\ket{\psi} = \cos(\theta) \ket{0} + e^{i \phi} \sin(\theta) \ket{1},
\end{equation}
where it can now be seen that only two real numbers are need to specify a pure qubit state: $\theta, \phi$. 

However, it can be seen that if $\theta = 0$ then $\ket{\psi} = \ket{0}$ and that if $\theta = \pi/2$ then $\ket{\psi} = e^{-i \phi} \ket{1}$, where, as before, the global phase can be ignored. All qubit states can therefore be generated via $0 \leq \theta \leq \pi/2$ and $0 \leq \phi \leq 2 \pi$. By convention, a general pure qubit state is considered to be 
\begin{equation}
\ket{\psi} = \cos\bigg(\frac{\theta}{2}\bigg) \ket{0} + e^{i \phi} \sin\bigg(\frac{\theta}{2}\bigg) \ket{1}: ~ ~ 0 \leq \theta \leq \pi, ~ ~ 0 \leq \phi \leq 2 \pi.
\end{equation}

The density matrix of this general pure qubit state is then found with respect to the standard basis,
\begin{align*}
\rho = \ket{\psi}\bra{\psi} 
&= \begin{pmatrix} \cos^{2}\bigg(\frac{\theta}{2}\bigg) & e^{-i \phi}  \cos\bigg(\frac{\theta}{2}\bigg) \sin\bigg(\frac{\theta}{2}\bigg) \\
e^{i \phi}  \cos\bigg(\frac{\theta}{2}\bigg) \sin\bigg(\frac{\theta}{2}\bigg) & \sin^2\bigg(\frac{\theta}{2}\bigg) \end{pmatrix},
\end{align*}
which, using the [trigonometric double angle formula](https://mathworld.wolfram.com/Double-AngleFormulas.html) and [Euler's formula](https://en.wikipedia.org/wiki/Euler%27s_formula), can be rewritten as
\begin{align*}
= \frac{1}{2}~\begin{pmatrix} 1 + \cos(\theta) & \big( \cos(\phi) - i \sin(\phi)\big) \sin(\theta) \\
\big( \cos(\phi) + i \sin(\phi)\big) \sin(\theta) & 1 - \cos(\theta) 
\end{pmatrix}.
\end{align*}
Finally, it can be seen that this can be written as a sum of Pauli-operators as 
\begin{align*}
&= \frac{1}{2} \biggl( \mathbb{I} + \big(\sin(\theta) \cos(\phi) \big) X + \big(\sin(\theta) \sin(\phi) \big) Y + \big( \cos(\theta) \big) Z \biggl), \\
&= \frac{1}{2} (\mathbb{I} + \bm{n} \cdot \bm{\sigma}).
\end{align*}

The qubit state is therefore uniquely specified by $\bm{n}$, which can be seen to be spherical polar coordinates. For these pure qubit states, the radius is always one. Each $\bm{n}$ therefore specifics a point on the surface of the unit sphere - there is a one to one mapping between point on the surface of the unit sphere and pure qubit states. 

**To show that each Bloch vector element is given by the expectation value of the respective Pauli operator** one just needs to sub in the Bloch vector form of $ \rho $ into the expectation value equation, 
\begin{align*}
\textrm{tr} \big[ \rho X \big] &= \frac{1}{2}~\textrm{tr} \big[ \big( \mathbb{I} + \bm{n} \cdot \bm{\sigma} \big) X \big], \\
&= \frac{1}{2}~\textrm{tr} \big[ X + n_x \mathbb{I} + n_y YX + n_z ZX \big], \\
&= \frac{1}{2}~n_x~\textrm{tr}\big[\mathbb{I}\big], \\
&= n_x,
\end{align*}
where the fact that the Pauli operators are traceless has been used. 

**Finally, mixed states are considered**. All mixed states can be written as a mixture of pure states, which each have their own Bloch form,
\begin{align*}
\rho &= \sum_{i} p_i \ket{\psi_i}\bra{\psi_i}, \\
&= \frac{1}{2} ~ \sum_{i} p_i \big( \mathbb{I} + \bm{n}_i \cdot \bm{\sigma} \big), \\
&= \frac{1}{2} \big( \mathbb{I} + \bigg(\sum_{i} p_i \bm{n}_i \bigg) \cdot \bm{\sigma} \big), \\
&= \frac{1}{2} \big( \mathbb{I} + \bm{n} \cdot \bm{\sigma} \big),
\end{align*}
where $\bm{n}$ is now take to be the mixture of Bloch vectors of each of the pure states in the description of $ \rho $. The norm of this Bloch vector is given by 
\begin{align*}
\vert \bm{n} \vert &= \bm{n} \cdot \bm{n}, \\
&= \sum_{i} \sum_j p_i p_j \bm{n}_i \cdot \bm{n}_j, \\
& \leq 1,
\end{align*}
as $ \bm{n}_i \cdot \bm{n}_j \leq 1~\forall~i,j$ and $\sum_{i} \sum_j p_i p_j \leq 1$ as $\sum_i p_i =1$, and similarly for $j$. Hence, the Bloch vectors of mixed states have a norm less than one. When considered with respect to the unit sphere, this means that mixed state sit inside the sphere. As with pure qubit states, there is a one to one mapping between points inside the sphere and mixed qubit states. 
:::

### Orthogonality 

Given a pure quantum state $\ket{\psi}$ with Bloch vector $ \bm{n} $, the orthogonal state $ \ket{\psi'}$, such that $ \braket{\psi|\psi'}=0$, has Bloch vector $-\bm{n}$. 

Hence, orthogonal pure state correspond to **the opposite point** on the bloch sphere. Perpendicular Bloch vectors **do not** mean orthogonal quantum states.  

:::{dropdown} Proof
:open:

Let 
\begin{equation}
\ket{\psi} = \cos\bigg(\frac{\theta}{2}\bigg) \ket{0} + e^{i \phi} \sin\bigg(\frac{\theta}{2}\bigg) \ket{1}.
\end{equation}
The state on the opposite of the Bloch sphere has 
\begin{equation}
\theta \rightarrow \pi - \theta, ~ ~ \phi \rightarrow \phi \pm \pi,
\end{equation}
giving the state 
\begin{align*}
\ket{\psi'} &= \cos\bigg(\frac{\pi - \theta}{2}\bigg) \ket{0} + e^{i \phi + i \pi} \sin\bigg(\frac{\pi - \theta}{2}\bigg) \ket{1}, \\
&= \cos\bigg(\frac{\pi - \theta}{2}\bigg) \ket{0} - e^{i \phi} \sin\bigg(\frac{\pi - \theta}{2}\bigg) \ket{1}.
\end{align*}
The inner product between these state is then 
\begin{align*}
\braket{\psi'|\psi} = &\biggl( \cos\bigg(\frac{\pi - \theta}{2}\bigg) \bra{0} - e^{-i \phi} \sin\bigg(\frac{\pi - \theta}{2}\bigg) \bra{1} \biggl) \\
&\times \biggl( \cos\bigg(\frac{\theta}{2}\bigg) \ket{0} + e^{i \phi} \sin\bigg(\frac{\theta}{2}\bigg) \ket{1}  \biggl), \\
&= \cos\bigg(\frac{\theta}{2}\bigg)\cos\bigg(\frac{\pi - \theta}{2}\bigg) - \sin\bigg(\frac{\theta}{2}\bigg) \sin\bigg(\frac{\pi - \theta}{2}\bigg), \\
&= \cos\bigg(\frac{\theta}{2}\bigg) \biggl[ \cos\bigg(\frac{\pi}{2}\bigg)\cos\bigg(\frac{\theta}{2}\bigg) + \sin\bigg(\frac{\pi}{2}\bigg)\sin\bigg(\frac{\theta}{2}\bigg) \biggl] \\
&  - \sin\bigg(\frac{\theta}{2}\bigg) \biggl[ \sin\bigg(\frac{\pi}{2}\bigg)\cos\bigg(\frac{\theta}{2}\bigg) - \cos\bigg(\frac{\pi}{2}\bigg)\sin\bigg(\frac{\theta}{2}\bigg) \biggl], \\
&= 0, 
\end{align*}
as
\begin{align*}
\sin\bigg(\frac{\pi}{2}\bigg) &= 1 ~ ~ \textrm{and} ~ ~ \cos\bigg(\frac{\pi}{2}\bigg) = 0, \\
\cos(x-y) &= \cos(x)\cos(y) + \sin(x)\sin(y), \\
\sin(x-y) &= \cos(x)\sin(y) - \cos(y)\sin(x).
\end{align*}

:::

### Higher Dimensions

There exists generalisations of the Bloch vector form to higher dimensional states, but the nice geometrical interpretation of points in a unit sphere is lost. 

In order to get a higher dimensional Bloch vector form, an operator basis is needed. Typically, in a $d$ dimensional space, an operator basis is a set of operators $d^2-1$ operators $\{ A_i \}$ such that 
1. $\mathbb{I} \in \{ A_i \}$.
    - The set contains the identity operator
2. $\textrm{tr} \big[ A_i^{\dagger}A_j \big] = N \delta_{ij}$, where $N \in \mathbb{R}$ and $\delta_{ij}$ is the delta function. 
    - The set of operators is orthogonal according to the Hilbert-Schmit inner product. 

In the qubit case, these set of operators were the identity and Pauli operators, $\{ \mathbb{I}, X, Y, Z \}$. 

Given $\{ A_i \}$ forms a [basis](#basis_page_target), any matrix can be decomposed into $\{ A_i \}$. For a density operators $ \rho \in \mathcal{H}^{d} $, it's density matrix with respect to $\{ A_i \}$ can be written as 
\begin{equation}
\rho = \frac{1}{d} \bigg( \mathbb{I} + \bm{b} \cdot \bm{\Sigma} \bigg),
\end{equation}
where $\bm{b} \in \mathbb{R}^{d^2-1}$ and $ \bm{\Sigma} $ is a vector whose elements are the operators in the basis, $\{ A_i \}$. Hence, $ \rho $ is written as linear combination of operators in the basis. 

As before, the $\frac{1}{d} \mathbb{I}$ term fixes the normalisation, such that $\textrm{tr}\big[ \rho \big] = 1$, and the components of the Bloch vector can be found as $b_i = \textrm{tr} \big[ \rho A_i \big]$.

However, not all Bloch vectors $\bm{b}$ correspond to valid density operators, as in the qubit case. 

There are multiple different operator basis one could choose and hence no unique Bloch vector for a given state. See the following for more details on different operator basis one could choose: http://dx.doi.org/10.1088/1751-8113/41/23/235303, https://journals.aps.org/pra/abstract/10.1103/PhysRevA.94.010301.

## Dynamics  