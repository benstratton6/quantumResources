---
title: Classical Error Correction 
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
keywords: bits, bit-flips, repetition code 
abstract: A brief overview of the terminology of error correction, including simple forms of classical error correction.  
exports:
#   - format: docx
  - format: pdf
    template: physical_review_journals
    article_type: Report
---

All information is encoded in physical systems. These physical systems are subject to noise - unwanted interactions with the environment - that can corrupt this encoded information. The goal of error correction is to combat this noise and hence ensure that the any encoded information is correctly decoded. 

## Noise in Classical Information Processing

Classical information is encoded into physical systems via a binary encoding, where the information is stored as a sequence of $\ket{0}$ and $\ket{1}$'s. The given information ones wants to encode is called the **logical information** and for $n$ bits this takes the forms of a bit-string from 
\begin{equation}
\mathfrak{B} = \{ \ket{0}, \ket{1} \}^n.
\end{equation} 

Once encoded, the logical information is either sent from one party to another, stored in a memory or processed to perform a computation. 

During these processes, the physical systems the logical information is encoded in will interact with the environment. This can have the effect of alternating the encoded logical information. Namely, **bit-flips** can occur, where an encoded $\ket{0}$ is flipped to a $\ket{1}$ or a $\ket{1}$ is flipped to a $\ket{0}$. This error can be modelled by the Pauli $X$ operator as
\begin{equation}
X \ket{0} = \ket{1}, ~~ X \ket{1} = \ket{0}, ~ ~ {\rm where} ~ ~X = \ket{0}\bra{1} + \ket{1}\bra{0}.
\end{equation}

After the information has been sent or stored in memory for some time, it needs to be decoded. In the absence of any noise, the decoded information will be the same as the encoded information. However, when noise occurs the information can be changed, leading to the incorrect information being decoded. Similarly, when performing a computation in the absence of noise, the correct output of the computation for the given input will be decoded. However, if noise has occurred during the computation, the incorrect output for the given input may be decoded. 

## Classical Error Correction

Error correction aims to combat noise through redundancy - each logical bit is instead encoded in many physical bits. A method of encoding logical information through redundancy in order to protect against errors is known as an **error correcting code**. 

### The Repetition Code

The simplest classical error correcting code is the 3-bit repetition code. Here, each bit of logical information is encoded via three physical bits of information. Specifically,
\begin{equation}
\ket{0}_{L} \rightarrow \ket{000}, ~~~ \ket{1}_L \rightarrow \ket{111}, 
\end{equation}
where the left side of the arrow is a bit of logical information, denoted by the subscript $L$, and the right hand side is the physical information. The bit-string of logical information $\ket{010}_L$ is therefore physically encoded as $\ket{000111000}$, where 9 physical bits are used to encode 3 logical bits. The bit-string $\ket{000}$ and $\ket{111}$ are called **logical codewords** of this error correcting code. 

Consider a logical bit, say $\ket{0}$, is sent from one party to another via a noisy channel that causes the first physical bit to be flipped,
\begin{equation}
\ket{0}_L = \ket{000} \xrightarrow{\rm Noisy~ Channel} (X \otimes \mathbb{I} \otimes \mathbb{I}) \ket{000} = \ket{100}.
\end{equation}

Upon receiving the three physical bits, a **majority vote** can then be used to identify if any errors have occurred. The three bits are read-out (measured) and the number of $\ket{0}$ and $\ket{1}$'s are counted. If there are more $\ket{0}$'s than $\ket{1}$'s then the logical information is decoded as $\ket{0}_L$ and vice versa. In the above example, there are two $\ket{0}$'s and one $\ket{1}$, so $\ket{0}_L$ is decoded. 

The 3 bit repetition code fails if a bit-flip (X) error occurs on more then one physical bit. For example, consider the following error on two physical bits, 
\begin{equation}
\ket{0}_L = \ket{000} \xrightarrow{\rm Noisy~ Channel} (X \otimes X \otimes \mathbb{I}) \ket{000} = \ket{110}.
\end{equation}
A majority vote will count one $\ket{0}$ and two $\ket{1}$'s, leading to $\ket{1}_L$ being decoded. A logical error will therefore have occurred, meaning an error has been applied to the logical information. If an error occurs on three physical bits then 
\begin{equation}
\ket{0}_L = \ket{000} \xrightarrow{\rm Noisy~ Channel} (X \otimes X \otimes X) \ket{000} = \ket{111},
\end{equation}
meaning the $\ket{0}_L = \ket{000}$ codeword is flipped to the $\ket{1}_L=\ket{111}$ codeword. A majority vote will therefore decode $\ket{1}_L$ without knowing an error as occurred. 

### Code Distance

This distance of a code is the minimum numbers of errors that will change one codeword to another. Alternatively, the distance of a code is the minimum number of errors that will go undetected. 

In the example of the repetition code, three physical errors take one code word to the other, meaning the distance of the code is three. Alternatively, it is when three physical errors occur that one does not even know an error has occurred, again leading to the conclusion that the code distance is three. 

There exists the following relationship between code distance, $d$, and correctable errors, t, 
\begin{equation}
d = 2t + 1.
\end{equation}

### Labelling Codes

Codes are labelled as
\begin{equation}
[ n: {\rm number of physicals}, k : {\rm number of logicals}, d: { \rm code distance}].
\end{equation}
