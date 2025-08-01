---
title: Haar Measure and t-Designs 
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
keywords:  
abstract: An overview of the Haar measure and t-designs 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

A measure is a mathematical object used to ensure elements of a space or set are properly weighted when that the space/set is integrated over or sampled from. Without a measure, the geometry of the space can lead to a bias in the sampling or an incorrect integral. 

### Spherical Measure 

When integrating and function over the surface of a sphere in polar coordinates, $(r, \theta, \phi)$, the measure $r^2 \sin{(\theta)}$ is used. It is necessary to use this measure to account for the fact that the area of a sphere defined by the same small change in $\theta$ and $\phi$, i.e $d \theta, d \phi$, is different for different $\theta$. The measure corrects for this by weighting points in the space differently, namely according to their value of $\theta$. Without it, if one sampled from the points on the surface of the sphere they would see a bias toward the poles.   

### Haar Measure 

The Haar measure is the measures used to correctly weight the unitary group. If one was to integrate over the unitary group they would need to use the Haar measure to ensure they get the correct result
\begin{equation}
\int_{v \in U} f(v) d \mu(v),
\end{equation}
where $f(\cdot)$ is a polynomial function, $U$ is the set of all unitaries and $d \mu(V)$ is Haar measure. If instead sampling from the unitary group, one needs to use the Haar measure to prevent a bias in the sample. 

If one samples from the unitary group using the Haar measure they typically refer to this as a Haar random unitary. By applying these to a fixed input state, such as $\ket{0}$, one can then generate Haar random states. 

See [](https://doi.org/10.22331/q-2024-05-08-1340) for a more complete overview of the Haar measure in quantum information theory.

### t-design

Using the Haar measure, one can evenly sample of the set of all unitaries. However, this is an infinite set, parametrised by a set of continuous parameters that increases exponentially in number with the size of the unitary. Practically, it is therefore very expensive if not impossible to generate a Haar random unitary. This motivates the question of whether there is a smaller set of unitaries that can be sampled from, with the output approximating a Haar random unitary. 

A unitary t-design is a set of unitaries able to exactly replicated the 

Designs can 



