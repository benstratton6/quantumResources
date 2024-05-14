---
title: Risk Aversion 
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
keywords: Utility, Risk, Risk Aversion.
abstract: A brief overview of risk aversion, including measures of risk aversion and it's meaning.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

Risk aversion can be thought of as an agents attitude toward risk. More formally, it models the tendency of people to prefer outcomes will low uncertainty to those with high uncertainty, even if the average payback from the higher uncertainty outcome is equal to or larger than the payback from the low uncertainty outcome. 

People will often agree to take an option that has low uncertainty and lower payoff, then high uncertainty but high payoff. For example, one could put there money in a bank account with reliable but low interest returns. Or, one could put there money into a stock that is volatile, but has a potentially high return. 

Risk aversion is encoded into the curvature of the [utility function](#utility_function_target_quantfinance):
(utility_function_curvature_target_quantFiance)=
- If $u(w)$ is concave then the agent being modelled is risk-adverse.
- If $u(w)$ is linear then the agent being modelled is risk-neutral.
- If $u(w)$ is convex then the agent being modelled is risk-seeking. 

The higher the curvature of the utility function, the higher the risk aversion/risk seeking. 

Whilst utility functions introduce the notion of risk, the concept of risk aversion allows one to quantify it. 

### Risk Aversion Measures

::::{tab-set}
:::{tab-item} Relative Risk Aversion
:sync: tab3
Let $u_{R}(w)$ be some utility function.

Relative Risk Aversion (RRA) of $u_{R}(w)$ is given by 
(RRA_utility_functions_target)=
\begin{equation}
\textrm{RRA} u_{R}(w) \coloneqq \frac{-w u_{R}''(w)}{u_{R}'(w)},
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

### Constant Risk Aversion

[Isoelastic utility](#isoelastic_utility_function_target) functions are functions that are unique in having constant [RRA](#RRA_utility_functions_target). This means that an agents attitude toward risk would not change if both the potential upsides and downsides were multiplied by some factor (meaning the ratio of upside to downside is constant). 

[Exponential utility](#exponential_utility_function_target) are functions that are unique in having constant [ARA](#ARA_utility_functions_target). This means that an agents attitude toward risk would not change if both the potential upsides and downsides were linearly scaled by some factor. More formally, this means an agents risk is independent of his liabilities (if the total amount of wealth an agent has changes, there attitude towards risk does not). 

Constant ARA is considered to be unrealistic, with people taking less risk if the downside is losing a larger portion of there limited wealth, and more risk if they have more wealth to lose. Consider an underpaid PhD who becomes a billionaire after commercialising their research. If modelled under constant ARA, they would worry about losing £10 just as much before and after they became a billionaire. If modelled under constant RRA, the student would worry about losing 10% of their wealth just as much before and after they became as billionaire. 

The difference between two agents with these risk profiles can be further demonstrated through a model where the agents have an investment portfolio where they have some in a risky (and hence probably high return) asset $A$ and some in a low risk (and hence probably low return) asset $B$. If an agent with constant ARA experiences an increase in wealth, they will keep the total amount of money they have in the risky asset constant. If an agent with constant RRA experiences an increase in wealth, they will keep the fraction of their portfolio they have in the risky asset constant.   