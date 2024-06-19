---
title: Quantum Channels
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
keywords: Dynamics, Channels, Evolution, Positive, Trace Preserving.   
abstract: The details of how the dynamics of quantum states are modelled.    
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

## Definition 

A quantum channel is a linear, completely positive, trace-preserving map (from the set of density operators to itself). 

A channel mapping from states in an input Hilbert space $\mathcal{H}_{in}$ to an output Hilbert space $\mathcal{H}_{out}$ is denoted as 
\begin{equation}
\mathcal{E}: \mathcal{H}_{in} \rightarrow \mathcal{H}_{out}
\end{equation}

### Linear 

A map, $\mathcal{E}$, is linear if 
\begin{equation}
\mathcal{E}(\rho + \sigma) = \mathcal{E}(\rho) + \mathcal{E}(\sigma)
\end{equation}

### Positive 

A linear map, $\mathcal{E}$, is positive if it maps positive elements to positive elements,
\begin{equation}
\rho \geq 0 \implies \mathcal{E}(\rho) \geq 0.
\end{equation} 


### Completely Positive   

A linear map, $\mathcal{E}$, is completely positive if it remains a positive map when embedded into a high dimensional space,
\begin{equation}
\rho \geq 0 \implies (\mathcal{E} \otimes \mathcal{I}) (\rho) \geq 0,
\end{equation} 
where $\mathcal{I}$ is the identity channel on an arbitrarily large ancilla. 

This additional restriction is needed to ensure that acting that map on part of a larger, potentially entangled state, still outputs a physical quantum state. 

This ensure that all operators output from a channel remain positive semi-definite. 

### Trace-preserving

A map, $\mathcal{E}$ is trace preserving if 
\begin{equation}
\textrm{tr} \big[ \mathcal{E}(\rho) \big] = 1,
\end{equation}
for all $\rho \in \mathcal{H}_{in}$, where $\rho$ is a valid density operator, $ \textrm{tr} \big[ \rho \big] = 1, \rho \geq 0$. 

This ensure that all operators output from a channel still have trace one.

## Channel Descriptions