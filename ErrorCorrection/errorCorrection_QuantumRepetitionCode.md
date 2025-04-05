---
title: Quantum Repetition Codes
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
keywords: qubits, Repetition Code, bit-flips, phase errors.  
abstract: The bit-flip and phase-flip quantum repetition codes.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

The Quantum Repetition Code comes in two flavours, one protects against bit-flip errors and the other protects against phase-flip errors. As with the classical repetition code, the code works increasing the size of the Hilbert space, allowing logical qubits to be encoded in multiple physical qubits.  



## The 2-Qubit Bit-flip Repetition Code

This code encodes one logical qubit in two physical qubits and is able to detect a single bit-flip $\big(X \big)$ error.

The code-words of the code are
\begin{equation}
\ket{0}_{L} \rightarrow \ket{00}, ~~~ \ket{1}_L \rightarrow \ket{11}, 
\end{equation}
such that an arbitrary qubit can be encoded as
\begin{align*}
\ket{\psi} = \alpha \ket{0} + \beta \ket{1} \xrightarrow{\rm encoder} \ket{\psi}_L = \alpha \ket{00} + \beta \ket{11}
\end{align*}
The part of the expanded Hilbert space in which the logical information is encoded is called the code space, given here by 
\begin{equation}
\mathfrak{C} = {\rm Span} \{ \ket{00}, \ket{11} \}.
\end{equation}
The aim of the code is to detect if an error on the physical qubits have caused the state to leave the code space without disturbing the encoded information. 

Consider measuring the following operator on the state,
\begin{align*}
Z_1 \otimes Z_2 &= \big( \ket{0}\bra{0} - \ket{1}\bra{1} \big) \otimes \big( \ket{0}\bra{0} - \ket{1}\bra{1} \big), \\
&= \ket{00}\bra{00} - \ket{01}\bra{01} - \ket{10}\bra{10} + \ket{11}\bra{11}, \\
&= \ket{\Phi_{00}^{+}}\bra{\Phi_{00}^{+}} + \ket{\Phi_{01}^{+}}\bra{\Phi_{01}^{+}} - \ket{\Phi_{10}^{+}}\bra{\Phi_{10}^{+}} - \ket{\Phi_{11}^{+}}\bra{\Phi_{11}^{+}},
\end{align*}
where in the final line $Z_1 \otimes Z_2$ has been written in its eigenbasis, namely the [Bell basis](#bell_states_teleportation_target).

Firstly, it can be seen that measuring $Z_1 \otimes Z_2$ on any state supported only within $\mathfrak{C}$ always gives a measurement outcome of $(+1)$ **and** returns the state unchanged, 
\begin{equation}
\big(Z_1 \otimes Z_2 \big)\big( \alpha \ket{00} + \beta \ket{11} \big) = \alpha \ket{00} + \beta \ket{11}.
\end{equation}
Consider now that an $X$-error occurs on the first qubit, 
\begin{equation}
X_1 \ket{\psi}_L = \alpha \ket{10} + \beta \ket{01}.
\end{equation} 
A measurement of $Z_1 \otimes Z_2$ on this state would give an outcome of $(-1)$. Likewise, if an $X$-error occurs on the second qubit, 
\begin{equation}
X_2 \ket{\psi}_L = \alpha \ket{01} + \beta \ket{10},
\end{equation} 
a measurement of $Z_1 \otimes Z_2$ would also give an outcome of $(-1)$. If, instead, an $X$-error occurs on both qubits,
\begin{equation}
X_1X_2 \ket{\psi}_L =  \alpha \ket{11} + \beta \ket{00},
\end{equation} 
then a measurement of $Z_1 \otimes Z_2$ would give an outcome of $(+1)$.

The outcome of measuring $Z_1 \otimes Z_2$ can therefore be used as a syndrome. If a single $X$ error occurs, then a measurement of $Z_1 \otimes Z_2$ is enough to detect that an error has occurred. Although, it is not enough to know if that error occurred on the first or the second qubit as both give the same measurement outcome. Therefore, the error cannot be corrected, only detected, as its location is not known. If, on the other hand, an $X$-error has occurred on both qubits, a measurement of $Z_1 \otimes Z_2$ is not enough to determine if an error has occurred. This is a result of the qubit remaining in $\mathfrak{C}$ under an $X_1X_2$ error and therefore leading to a measurement result of $(+1)$. This situation is therefore indistinguishable from no error having occurred.  

In addition to not being able to detect $X_1X_2$ error, 2-qubit bit-flip repetition code is also unable to protect against phase errors ($Z$-errors). For example, consider the error 
\begin{equation}
Z_1 \ket{\psi}_L = \alpha \ket{00} - \beta \ket{11}_L.
\end{equation}
A measurement of $Z_1 \otimes Z_2$ would give an outcome of $(+1)$ as this state remains in $\mathfrak{C}$. Hence, a $Z_1$ error is indistinguishable from no error having occurred and hence cannot be detected. The same if true of a $Z_2$ error. 

The 2-qubit bit-flip repetition code is therefore only useful for detecting the errors $\{\mathbb{I}, X_1, X_2 \}$. 

## The 3-Qubit Bit-flip Repetition Code

The code encodes one logical qubit in three physical qubits and is able to **correct** one bit-flip error, but detect up to two bit-flip errors.