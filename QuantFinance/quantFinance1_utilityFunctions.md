---
title: Utility Functions 
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
keywords: Utility, Expected Utility, Risk.
abstract: A brief overview of utility functions, there uses, properties and some examples.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

### Utility

Utility is used to model total satisfaction or benefit gained from having a certain wealth, consuming a good or consuming a service. Theories based off the idea of a rational consumer usually assume that people will try and maximise their utility, that is, maximise their total satisfaction. It is often used to evaluate situations without an immediate pay back and uncertainty in the outcome. 

Utility directly influences demand, as the higher the utility of a product or service the more consumers will want it. As a consequence, utility also influences the price of a good or service. 
(utility_function_target_quantfinance)=
### Utility Functions

Assume there is some set of possible alternatives, $\mathfrak{W} = \{ w_{i} \}$, form which an agent can either choose from, or be assigned (situation dependent). The set $\mathfrak{W}$ has a binary relation, $>$, that allows any two elements of the set to be compared. This binary relation models the agents preference, with the agent preferring $w_{i}$ to $w_{j}$ if $w_i > w_j$. It is also assumed that possible alternatives can be mixed according to some probability distribution and give a legitimate alternative for agent, such that 
\begin{equation}
\alpha w_{i} + (1-\alpha) w_{j} \in \mathfrak{W}~\forall~ \alpha \in [0,1].
\end{equation}

A utility function is a function that maps from the set $\mathfrak{W}$ to the real numbers, whilst preserving the ordering set by the binary relation. 

Hence, $u: \mathfrak{W} \rightarrow \mathbb{R}$, such that 
\begin{equation} 
u(w_{i})>u(w_{j})~ ~  \textrm{if} ~ ~  w_{i}>w_j.
\end{equation} 
Formally, this means that utility functions are a monotone for the binary relation.  

The utility function subject to a linear transformation will continue to be monotonic for the binary relation. Hence, the numerical output of a utility function does not hold any intrinsic value. It is comparisons between the utility of different alternatives that has meaning.   

Utility functions allow the idea of risk to be introduced to the agents. Typically, they will include an additional parameter $R$ that is used to model the agents attitude toward risk.   

:::{dropdown} Utility Axioms
:closed:

Let $\mathfrak{W} = \{ w_{i} \}$ be a set of alternative outcomes. 

There exists a binary relation on $\mathfrak{W}$, namely $>$, and alternative outcomes and be combined via some probability distribution $\alpha \in [0,1]$ to form new alternative outcomes, 
\begin{equation}
w' = \alpha w_{i} + (1-\alpha) w_{j} \in \mathfrak{W}.
\end{equation} 

These concepts satisfy the following axioms:

1. $w_{i} > w_j$ forms a [total ordering](#total_ordering_preorder_maths_notes_target) on $\mathfrak{W}$. 

This means that for all pairs of elements, $(w_{i}. w_{j})$ in $\mathfrak{W}$ one of the following relations is true
\begin{equation}
w_i = w_j, ~ ~ w_i > w_j ~ ~ w_i < w_j
\end{equation}
and if $w_{i} > w_j$ and $w_{j} > w_k$ then $w_i > w_k$.

  - **Physical Interpretation**: The agent has a preference over all possible alternatives. There is no set of possible alternative where they are "not sure" which alternative they prefer. 

2. $w_i < w_j$ implies $w_i < \alpha w_i + (1-\alpha) w_j$

  - Physical Interpretation: If $w_j$ is preferable to $w_i$ then having any probability of obtaining the alternative $w_j$ is preferable to having $w_i$ with certainty. 

3. $w_i > w_j$ implies $w_j > \alpha w_i + (1-\alpha) w_j$

  - **Physical Interpretation**: If $w_i$ is preferable to $w_j$ then having any probability of obtaining the alternative $w_j$ is less-preferable to having $w_i$ with certainty. This is the alternative case to 2. 

4. $w_i < w_j < w_k$ implies the existence of an $\alpha$ such that 
\begin{equation}
\alpha w_i + (1-\alpha) w_k < w_j
\end{equation}

  - **Physical Interpretation**: Regardless of how preferable $w_k$ is to compared $w_j$, there exists a probability of $w_k$ occurring that is small enough compared to the probability of the less preferable alternative $w_i$ occurring such that taking the chance is less preferable then $w_j$.  

5. $w_i > w_j > w_k$ implies the existence of an $\alpha$ such that 
\begin{equation}
\alpha w_i + (1-\alpha) w_k > w_j
\end{equation}

  - **Physical Interpretation**: Regardless of how less preferable $w_k$ is to compared $w_j$, there exists a probability of $w_k$ occurring that is small enough compared to the probability of the more preferable alternative $w_i$ occurring such that taking the chance is more preferable then $w_j$.  

If these axioms are satasfied then there exists a function $u: \mathfrak{W} \rightarrow \mathbb{R}$ that preserve the ordering set on $\mathfrak{W}$ by the binary relation.

These axioms were taken from [Theory of Games and Economic Behavior](https://books.google.co.uk/books?id=jCN5aNJ-n-0C)

:::

### Expected Utility

In general, one assumes that there is some probability distribution of the potential alternatives, with the alternative $w \in \mathfrak{W}$ occuring with probability $p_w$ such that 
\begin{equation}
\sum_{w \in \mathfrak{W}} p_{w} = 1.
\end{equation}
From this probability distribution, one can consider the expected alternative as 
\begin{equation}
\mathbb{E}(\mathfrak{W}) = \sum_{w \in \mathfrak{W}} p_{w}w.
\end{equation}
This is the average alterative the agent would get if they sampled from the alternatives according to the probability distribution over them [💭](#example_expected_utlity_theory_quanntFinace_glossary).

The utility of this expected alternative if then given by $u \big[ \mathbb{E}(\mathfrak{W}) \big]$. 

The utility of each outcome is also described by some probability distribution. This means that the **expected utility** can be found from 
\begin{equation}
\mathbb{E} \big[ u(\mathfrak{W} ) \big] = \sum_{w \in \mathfrak{W}} p_{w} u(w).
\end{equation}

A rational agent will aim to maxamise their expected utility.

### Certainty Equivalent    

The certainty equivalent, $w^{CE}$, is the alternative that the agent is as satisfied with as the expected alternative, 
\begin{equation}
u(w^{CE}) = \mathbb{E} \big[ u(\mathfrak{W}) \big].
\end{equation}
The certainty equivalent is the alternative such that the utility of that alternative would give the agent the average utility over all alternatives. Hence, if the agent were offered the alternative $w^{CE}$ this would return them the expected amount of satisfaction (the expected utility)

### Risk from Utility

Consider that there is a probability distribution over all alternatives, with probability $p_{w}$ of getting an outcome $w \in \mathfrak{W}$. All the alternatives are totalled ordered due to preference, so this is some probability of getting a high ranked preference, and some probability of getting a low ranked preference.  

Assume that an agent can either choose an alterative from the distribution, or they choose to take the alterative given by the certainty equivalent, $w^{CE}$, alternative with certainty.  

How the certainty equivalent, $w^{CE}$, relates to the expected alternative, $\mathbb{E}(\mathfrak{W})$, tell us about the risk profile of the agent. 

- If $w^{CE} < \mathbb{E}(\mathfrak{W})$ the agent is risk adverse. 
  - The agent is cautious, they are happy to accept a definite alterative that is less preferable then the alternative they are expect to get from the distribution. This is to avoid the possibility of getting an even less preferable alternative. 
- If $w^{CE} = \mathbb{E}(\mathfrak{W})$ the agent is risk neutral. 
  - The agent will just choose whichever option will give them the most preferable alternative, even one only gives the most preferable alternative on average. 
- If $w^{CE} > \mathbb{E}(\mathfrak{W})$ the agent is risk seeking.
  - The agent is not cautious, they will only take the definite alternative if it is more preferable then the alternative they are expect to get from the distribution. This is because they are happy to take the possibility of getting a less preferable alternative in the hope of getting a more preferable alternative.  

These risk profiles are encoded into the [curvature of the utility functions](#utility_function_curvature_target_quantFiance). 

### Example Utility Functions 

::::{tab-set}
:::{tab-item} Isoelastic Utility
:sync: tab1
Let $w$ be some variable of importance to an agent and $R$ a parameter that models risk. 

An example of an isoelastic utility function is
(isoelastic_utility_function_target)=  
\begin{equation}
u_{R}(w) \coloneqq \left\{
	\begin{array}{ll}
		\frac{w^{1-R} - 1}{1-R}  & \mbox{if } R \geq0, R \neq 1 \\
		\ln{w} & \mbox{if } R = 1
	\end{array}
\right.
\end{equation}
:::
:::{tab-item} Exponential Utility
:sync: tab2

Let $w$ be some variable of importance to an agent and $R$ a parameter that models risk. 

An example of an exponential utility function is  
(exponential_utility_function_target)=
\begin{equation}
u_{R}(w) \coloneqq \left\{
	\begin{array}{ll}
		\frac{1}{R}(1-e^{-Rw})  & \mbox{if } R \neq 0 \\
		w & \mbox{if } R = 0
	\end{array}
\right.
\end{equation}

$R$ is the degree of risk preference
- $R > 0$ and the agent is risk-averse. 
- $R = 0$ and the agent is risk-neutral.
- $R < 0$ and the agent is risk-seeking. 

```{figure} exponential_utility_risk_profile.png
:alt: 
:class: bg-primary
:width: 500px
:align: center
:target: exponential_utility_risk_profile_target

How the exponential utility functions changes with varying risk parameter, $R$. 
```

:::
::::

