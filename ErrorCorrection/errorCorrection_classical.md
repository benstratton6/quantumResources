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

All information is encoded in physical systems. Such systems are subject to noise - unwanted interactions with the environment - that can corrupt this encoded information. The goal of error correction is to combat this noise and hence ensure that the encoded information is correctly decoded. 

## Noise in Classical Information Processing

Classical information is encoded into physical systems via a binary encoding, where the information is stored as a sequence of $0$ and $1$'s. The given information ones wants to encode is called the logical information. 

Once encoded, the logical information is either sent from one party to another, stored in a memory or processed to perform a computation. 

During these processes, the physical systems the logical information is encoded in will interact with the environment. This can have the effect of alternating the encoded logical information. Namely, **bit-flips** can occur, where an encoded $0$ is flipped to a $1$ or a $1$ is flipped to a $0$.   

After the information has been sent or spent sometime in a memory it needs to be decoded. In the absence of any noise, the decoded information will be the same as the encoded information. However, when noise occurs the information can be changed, leading to the incorrect information being decoded. Similarly, when performing a computation in the absence of noise, the correct output of the computation for the given input will be decoded. However, if noise has occurred during the computation, the incorrect output for the given input may be decoded. 

## Classical Error Correction - The Repetition Code

Error correction aims to combat noise through redundancy - each logical bit is instead encoded in many physical bits. A method of encoding logical information through redundancy in order to protect against errors is known as an **error correcting code**. 

### The Repetition Code

The simplest classical error correcting code is the 3-bit repetition code. Here, each bit of logical information is encoded via three physical bits of information. Speciifcally,
\begin{equation}
0 \rightarrow 000, ~~~ 1 \rightarrow 111, 
\end{equation}
where the left side of the arrow is a bit of logical information and the right hand side is the physical information. The bit-string of logical information $010$ is therefore physically encoded as $000111000$. 

