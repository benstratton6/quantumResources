---
title: Groups  
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
keywords: Groups, Group Theory. 
abstract: A brief overview of discrete groups and some important group theory concepts. 
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

There is much literature on groups, these particular notes were made using [](https://doi.org/10.48550/arXiv.2605.29137) and only pertain to discrete groups.

## Group Definition

Consider a set $G$ and a [binary operation](#binary_operation_glossary) $* :  G \times G \rightarrow G$. Then $(G, *)$ is a group if the following conditions hold: 
(group_page_group_definition)=
1. $(a * b) * c = a * (b * c), ~ ~ a,b,c \in G$
    - Associativity 
2. $ \exists ~ e \in G$ such that $e * g = g * e~\forall~g \in G$
    - Unique identity element
3. $ \forall a \in G, ~ ~\exists~b \in G$ such that $a * b = b * a = e$.
    - Unique inverse element denoted as $a^{-1}$ for $a \in G$. 

## Abelian Groups

Let $(G, *)$ be a group. For $a,b \in G$, it is said that $a$ and $b$ commute if $a * b = b*a$. 

A group is said to be abelian if all elements of $G$ mutually commute. If not, it is said to be non-abelian. 

## Subgroups 
(group_page_subgroup_definition)=
Let $(G, *)$ be a group. Given a subset $H \subseteq G$, then $(H, *)$ is a subgroup of $(G, *)$ if $(H, *)$ is [group](#group_page_group_definition). 

## Cosets

Let $(G, *)$ be a group and let $(H, *)$ be a [subgroup](#group_page_subgroup_definition) of $(G, *)$. 

For an element $g \in G$:
(group_theory_page_cosets_definition)=
- The left coset of $(H, *)$ containing $g$ is $gH = \big\{ g*h : h \in H \big\}$
- The right coset of $(H, *)$ containing $g$ is $Hg = \big\{ h*g : h \in H \big\}$

Cosets shift a subgroup within the global group.

### Properties

- If the group $(G, *)$ is abelian, then the left and right coset are the same. 

- Two cosets are either the same, or they are disjointed (they do not overlap at all). Formally, let $a,b \in G$, then 
\begin{equation}
aH \cap bH \neq \emptyset ~ ~ &\implies aH = bH \\
aH \neq bH ~ ~ &\implies aH \cap bh \neq \emptyset \\
\end{equation}
:::{dropdown} Proof

Let $(G, *)$ be a [group](#group_page_group_definition) and let $(H, *)$ be a [subgroup](#group_page_subgroup_definition) of $(G, *)$. Then, let 
\begin{align*}
aH &\coloneqq  \big\{ a * h : h \in H \big\} \\
bH &\coloneqq \big\{ b * h : h \in H \big\}
\end{align*}
Now, assume that there exists an $x \in G$ such $x \in aH$ and $x \in bH$, meaning that the cosets intersect. 

By definition, there therefore exists a $h_1, h_2 \in H$ such that $x = a*h_1$ and $x = b*h_2$. 

Using the properties of a group, it therefore holds that $b^{-1}*a = h_1^{-1}*h_2$.

As $(H, *)$ is a group, it therefore also holds that $h_1^{-1}*h_2 = b^{-1}*a \in H$. 

One can therefore write $a = b*(b^{-1}*a)$, and see that $a$ is equal to $b$ up to some element $h \in H$, meaning that $a \in bH$. 

One can therefore concluded that $aH \subseteq bH$. Running the argument in reverse, one gets that $bH \subseteq aH$, such that $aH=bH$. The same argument works for the right cosets, which completes the proof. 
:::

- Due to the above, each element of $G$ is in exactly one coset.

- $(H, *)$ is a coset of $(G, *)$ where the considered element is the identity $e \in G$, i.e., $eH=H$. This is the only coset that is a subgroup, as it is the only coset containing $e$. 

- Each coset is equal in size, and they therefore split $G$ into equal sized, disjointed subsets. See [here](https://en.wikipedia.org/wiki/Lagrange%27s_theorem_(group_theory)) for more details.

<!-- ## Equivalence Relations -->

## Normal Subgroups
(group_page_normal_subgroup_target)=
A [subgroup](#group_page_subgroup_definition) $(N, *)$ of $(G, *)$ is called normal if $\forall g \in G$ it holds that
\begin{equation}
gN = Ng,
\end{equation}
meaning that the left and right [cosets](#group_theory_page_cosets_definition) are equal. 

This is true if $\forall g \in G$ it holds that $g N g^{-1} =  N$, meaning that 
\begin{equation}
\big\{ g * n_i * g^{-1} : n_i \in N \big\} = N,
\end{equation} 
such that taking every element of the set $N$ and conjugating it by $g$ gives back the set $N$. Note, this is a weaker notion then all elements commuting. 

## Quotient Groups

Let $(G, *)$ be a [group](#group-definition) and let $(H, *)$ be a [normal subgroup](#group_page_normal_subgroup_target) of $(G, *)$. 

The quotient group of $(G, *)$ with respect to $(H, *)$ is defined to be the group whose elements are all the left cosets of $H$: 
\begin{equation}
G/H \coloneqq \big\{ gH : g \in G \big\},
\end{equation}
with the binary operation being 
\begin{equation}
(g_1 H) \cdot (g_2 H) = (g_1 * g_2) H.
\end{equation}

As $(H, *)$ is normal, the left and right cosets are equal. Hence, the quotient group could also be defined via the right cosets. 

Moreover, normality of $(H, *)$ ensures that this binary operation is well defined. 
:::{dropdown} Proof

Let $a,b,c,d \in G$ such that $aH=cH$ and $bH=dH$ i.e., $c \in aH$ and $d \in bH$. 

The binary operation should be consistent if considered with respect to this alternative definition of the same coset. To see that this holds if $(H, *)$ is normal consider 
\begin{align*}
(a H) \cdot (b H) &= (a * b) H \\
&= a(bH) \\
&= a(dH) \\
&= a(Hd) \\
&= (aH)d \\
&= (cH)d \\
&= (cd)H.
\end{align*}.
:::  

Conceptually, a quotient group can be considered to be viewing the group $(G, *)$ modulo the group $(H, *)$. In this new group, $(H, *)$ is $e$ (the identity).
<!-- , with all elements in the group considered to be equivalent.     -->

<!-- ## Group Generators -->

## Group Examples

::::{tab-set}
:::{tab-item} Integers/addition 
:sync: tab1

Let $\mathbb{Z}$ be the set of all integers. Let $+$ be the binary operation of addition. Then $(\mathbb{Z}, +)$ is a group. 

:::
:::{tab-item} Invertible real matrices/multiplication
:sync: tab2

Let $\mathbb{M}_n$ be the set of $n \times n$ invertible matrices. Let $\times$ be the binary operator of [matrix multiplication](#traget_matrix_multiplication). Then $(\mathbb{M}_n, \times)$ is a group.  

:::
:::{tab-item} n-qubit Pauli Group
:sync: tab3

The elements of the $n$-qubit Pauli group $\mathcal{P}_n$ are the $n$-fold tensor product of single qubit Pauli-strings with all possible phases:
\begin{equation}
\mathcal{P}_n = \big\{ \mathbb{I}, X, Y, Z \big\}^{\otimes n} \times \{\pm 1, \pm i\}.
\end{equation}
The binary operator is then multiplication. 

See the [Pauli-group page](#Pauli_group_page_target) for more details.  

:::
::::



