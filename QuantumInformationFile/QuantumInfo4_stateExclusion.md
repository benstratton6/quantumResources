---
title: Quantum State Exclusion
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
keywords: State Exclusion, State Discrimination, POVMs, games.  
abstract: Details of the task of quantum state exclusion.   
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---
(state_exclusion_page_target)=
### State Exclusion Overview 

In a state exclusion task, a referee has a set of states $\{\rho_{x} \}^{N}, ~ x \in \{1, \ldots ,N\}$ and sends one state from the set, with probability $p_{x}$, to a player. The player then performs a general $N$ outcome measurement on the state, as described by a positive operator-valued measure (POVM) $\{T_{g}\}_{g=1}^{N}$, where $T_g\ge0$ $\forall\,g$ and $\sum_gT_g=\mathbb{I}$. From this measurement, the player outputs a label $g \in \{1, \ldots , N\}$. The player wins the task if $g \neq x$ and fail if $g=x$. Namely, they win if they successfully exclude the state by outputting a label that was not associated to the sent state; the player fails if they output the label associated to the sent state (https://link.aps.org/doi/10.1103/PhysRevA.66.062111, https://doi.org/10.1038/nphys2309, http://dx.doi.org/10.1103/PhysRevA.89.022336). 

### 1-State Exclusion
If the player outputs a single label $g$ such that $g \neq x$ with certainty, this is conclusive $1$-state exclusion. This occurs if the player is able to find a POVM such that  
\begin{equation}
    \textrm{tr} \big[ T_{x}\rho_{x}] = 0 ~ ~ \forall ~~ x  \in \{1, \ldots ,N\}. \label{stateExclusionEquation}
\end{equation}
If the player gets the measurement outcome associated to $T_{g}$, they output $g$ knowing with certainty the referee could not have sent $\rho_{g}$.

In general, a POVM may not exists that can perform conclusive state exclusion. Instead, state exclusion can be performed with some error, as given by the following SPD: 
\begin{align*}
    \min &~~ P_{err} = \sum^{N}_{g}  \textrm{tr} \big[T_{g} \rho_{g}] \\
    \textrm{Subject to:}& ~ ~  \sum^{N}_{g} T_{g} = \mathbb{I}, ~~ T_{g} \geq 0 ~ \forall ~ g, 
\end{align*}
where $P_{err}$ is the probability of making an error when performing exclusion, meaning the probability of outputting the index $g=x$. 

### k-State Exclusion

If the player outputs a set of $k$ labels, $\{ g_{i} \}^{k}$, such that $g_{i} \neq x ~ \forall ~ g_{i} \in \{g_{i}\}^{k}$ with certainty, this is conclusive $k$-state exclusion. There are $N \choose k$ different sets of $k$ labels the player could exclude, corresponding to all the different subsets of $\{1,\ldots,N\}$ of length $k$. Therefore, when performing $k$-state exclusion the player aims to find a POVM with $N \choose k$ elements such that each measurement outcome allows the player to exclude a subset of states from $\{\rho_{x} \}^{N}$ of length $k$. 

#### k-State Exclusion as 1-State Exclusion

All $k$-state exclusion tasks can be recast as $1$-state exclusion tasks by reformulating the set $\{\rho_{x}\}^{N}$ [](http://dx.doi.org/10.1103/PhysRevA.89.022336). Conceptually, this means all $k$-state exclusion tasks have a $1$-state exclusion task that they are dual to, allowing all state exclusion tasks to be studied under the $1$-state exclusion framework. 

Let $Y_{(N, k)}$ be the set of all subsets of the integers $\{1,2,...,N\}$ of length $k$. The player aims to measure a POVM on a state $\sigma \in \{ \rho_{x} \}^{N}$, given to them by the referee, and output a set of labels $Y \in Y_{(N,k)}$ such that $\sigma \notin \{ \rho_{y} \}_{y \in Y}$. Such a measurement will be a POVM with $a = {N \choose k}$ terms as there are $a$ subsets of $\{1,2,...,N\}$ of length $k$. For each elements of this POVM, $S = \{S_{l}\}^{a}_{l=1}$, the following equation must hold, 
\begin{equation}
    \textrm{tr}\big[S_{Y}\rho_{y}] = 0 ~ \forall ~y~ \in~ Y. \label{multiStateExclusionEquations}
\end{equation}
By defining 
\begin{equation}
    \rho_{Y} = \sum_{y \in Y} \rho_{y}, 
\end{equation}
the $k$-state exclusion task can be expressed as the following set of equations
\begin{equation}
    \textrm{tr} \big[ S_{Y} \rho_{Y}] = 0 ~\forall~Y \in Y_{(N,K)}. 
\end{equation}
This is now the same form as the $1$-state exclusion task conditions. This is the dual $1$-state exclusion task to the $k$-state exclusion task. 

Using the dual $1$-state exclusion task, $k$-state exclusion can also now be formulated as an SPD: 
\begin{align*}
    \min & ~~ P^{k}_{err} = \sum_{Y} \textrm{tr}[S_{Y}\rho_{Y}] \\
    \textrm{Subject to:}& ~ ~ \sum^{N}_{i} S_{i} = \mathbb{I}, ~~ S_{i} \geq 0 ~ \forall ~ i,
\end{align*}

where $P^{k}_{err} > 0$ if no POVM to conclusively perform $k$-state exclusion exists. 



