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

Utility is used to model total satisfaction or benefit gained from consuming a good or service. Theories based off the idea of a rational consumer usually assume that people will try and maximise their utility, that is maximise their total satisfaction. 

Utility directly influences demand, as the higher the utility of a product or service the more consumers will want it. Hence, utility also influences the price of a good or service. 

The utility of some agent with respect to some variable, $w$, can be modelled by a function $u(w)$. It typical includes an additional parameter $R$ that is used to model the agents attitude toward risk.   

### Expected Utility

This is the aggregate utility of an entity. It is often used to evaluate situations without an immediate pay back. 

Let $p_{x}$ be the probability of an outcome with utility $u(x)$ occurring. An rational consumer will aim to  
\begin{align*}
\max U = \sum_{x} p_{x} u(x), ~ ~ \textrm{where} ~ ~ \sum_{x} p_{x} = 1.
\end{align*}

### Certainty Equivalent    

### Example Utility Functions 

::::{tab-set}
:::{tab-item} Isoelastic Utility
:sync: tab1
Let $w$ be some variable of importance to an agent and $R$ a parameter that models risk. 

An example of an isoelastic utility function is  
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

### Risk Aversion 

Risk aversion can be thought of as an agents attitude toward risk. More formally, it models the tendency of people to prefer outcomes will low uncertainty to those with high uncertainty, if if the average payback from the higher uncertainty outcome is equal to larger to the payback from the low uncertainty outcome. 

People will often agree to take an option that has low uncertainty and lower payoff, then high uncertainty but high payoff. For example, one could put there money in a bank account with reliable but low interest returns. Or one could put there money into a stock that is volatile, but has a potentially high return. 

Risk aversion is encoded into the curvature of the utility function:

- If $u(w)$ is concave then the agent being modelled is risk-adverse.
- If $u(w)$ is linear then the agent being modelled is risk-neutral.
- If $u(w)$ is convex then the agent being modelled is risk-seeking. 

The higher the curvature of the utility function, the higher the risk aversion. 

### Risk Aversion Measures

::::{tab-set}
:::{tab-item} Relative Risk Aversion
:sync: tab3
Let $u_{R}(w)$ be some utility function.

Relative Risk Aversion (RRA) of $u_{R}(w)$ is given by 
(RRA_utility_functions_target)=
\begin{equation}
\textrm{RRA} u_{R}(w) \coloneqq \frac{-R u_{R}''(w)}{u_{R}'(w)},
\end{equation}

where $u_{R}''(w)$ and $u_{R}'(w)$ are the second and first derivatives of the utility function with respect to $w$. 

:::
:::{tab-item} Absolute Risk Aversion
:sync: tab4
Let $u_{R}(w)$ be some utility function.

Absolute Risk Aversion (ARA) of $u_{R}(w)$ is given by 
(ARA_utility_functions_target)=
\begin{equation}
\textrm{ARA} u_{R}(w) \coloneqq \frac{-u_{R}''(w)}{u_{R}'(w)},
\end{equation}

where $u_{R}''(w)$ and $u_{R}'(w)$ are the second and first derivatives of the utility function with respect to $w$. 

:::
::::

Isoelastic utility are functions that are unique in having constant [RRA](#RRA_utility_functions_target). This means that an agents attitude toward risk would not change if both the potential upsides and downsides were multiplied by some factor (meaning the ratio of upside to downside is constant). 

Exponential utility are functions that are unique in having constant [ARA](#ARA_utility_functions_target). This means that an agents attitude toward risk would not change if both the potential upsides and downsides were linearly scaled by some factor. More formally, this means an agents risk is independent of his liabilities (if the total amount of wealth an agent has changes, there attitude towards risk does not). This is considered to be unrealistic, with people taking less risk if the downside is losing more of their wealth. 

The difference between two agents with these risk profiles can be summed up through a model where the agents have an investment portfolio where they have some in a risky (and hence probably high return) asset $A$ and some in a low risk (and hence probably low return) asset $B$. If an agent with constant ARA experiences an increase in wealth, they will keep the total amount of money they have in the risky asset constant. If an agent with constant RRA experiences an increase in wealth, they will keep the fraction of their portfolio they have in the risky asset constant.   