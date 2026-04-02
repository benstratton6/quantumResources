---
title: Books
subject: Tutorial
kernelspec:
  name: python3
  display_name: Python 3
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
abstract: Books I have read and (potentially) enjoyed 
# exports:
#   - format: docx
  # - format: pdf
    # template: physical_review_journals
    # article_type: Report
---

```{code-cell} python
:tag: remove-cell

import matplotlib.pyplot as plt
import numpy as np
```

```{code-cell} python
:tags: [remove-input]

# Data for plotting
t = np.arange(0.0, 2.0, 0.01)
s = 1 + np.sin(2 * np.pi * t)

fig, ax = plt.subplots()
ax.plot(t, s)

ax.set(xlabel='time (s)', ylabel='voltage (mV)',
       title='Waves in Time')
ax.grid()

fig.savefig("test.png")
plt.show()
```

Here are a list of books I have read since 2021 with a (1-5)⭐ rating:

  - 1 ⭐ : Not Good
  - 2 ⭐ : Okay
  - 3 ⭐ : Enjoyable 
  - 4 ⭐ : Good 
  - 5 ⭐ : Excellent 

Within each genre, they are roughly in the order in which I read them. 

🛸 marks books read in the current year. 

# Fiction 

## Fantasy 

- **The Fellowship of the Ring**, _John.R.R Tolkien_, 4 ⭐
- **The Two Towers**, _John.R.R Tolkien_, 4 ⭐
- **The Return of the King**, _John.R.R Tolkien_, 4 ⭐
- **The Hobbit**, _John.R.R Tolkien_, 5 ⭐

## Science Fiction 

- **Dune**, _Frank Herbert_, 5 ⭐
- **Dune Messiah**, _Frank Herbert_, 4 ⭐
- **Children of Dune**, _Frank Herbert_, 2 ⭐
- **The Player of Games**, _Iain Banks_, 4 ⭐
- **Earthlight**, _Arthur C. Clarke_, 3 ⭐
- **Foundation**, _Isaac Asimov_, 5 ⭐
- **Forever War**, _Joe Haldeman_, 4 ⭐
- **Second Foundation**, _Isaac Asimov_, 4 ⭐
- **Foundation and Empire**, _Isaac Asimov_, 3 ⭐
- **The Early Asimov - Volume 1**, _Isaac Asimov_, 3 ⭐
- **Fahrenheit 451**, _Ray Bradbury_, 3 ⭐
- **Brave New World**, _Aldous Huxley_, 4 ⭐
- **I, Robot**, _Isaac Asimov_, 4 ⭐
- **Project Hail Mary**, _Andy Weir_, 5 ⭐
- **Starship Troopers**, _Robert A. Heinlein_, 4 ⭐
- **Foundations Edge**, _Isaac Asimov_, 3 ⭐
- **The Three Body Problem**, _Liu Cixin_, 5 ⭐
- **The Dark Forest**, _Liu Cixin_, 4 ⭐
- **Deaths End**, _Liu Cixin_, 4 ⭐
- **Slaughterhouse-Five**, _Kurt Vonnegut Jr._, 5 ⭐
- **The Dispossessed**, _Ursula K. Le Guin_, 5 ⭐
- **The Left Hand of Darkness**, _Ursula K. Le Guin_, 4 ⭐
- **Revelation Space**, _Alastair Reynolds_, 4 ⭐
- **Altered Carbon**, _Richard K. Morgan_, 5 ⭐
- **Old Mans War**, _John Scalzi_, 3 ⭐
- **Snow Crash**, _Neal Stephenson_, 3 ⭐ 🛸
- **War of the Worlds**, _H.G.Wells_, 3 ⭐ 🛸

## Spy 

- **Damascus Station**, _David McCloskey_, 4 ⭐
- **The Spy Who Came in from the Cold**, _John le Carré_, 5 ⭐ 🛸
- **Tinker, Tailor, Soldier, Spy**, _John le Carré_, 5 ⭐ 🛸

## Other 

- **Where The Crawdads Sing**, _Delia Owens_, 5 ⭐
- **A Kestrel for a Knave**, _Barry Hines_, 4 ⭐

# Non-Fiction

## Science 

- **Life 3.0**, _Max Tegmark_, 4 ⭐
- **Regenesis: Feeding the World Without Devouring the Planet**, _George Monbiot_, 4 ⭐
- **The Order of Time**, _Carlo Rovelli_, 3 ⭐
- **The Rise and Fall of the Dinosaurs**, _Steve Brusatte_, 5 ⭐

## Politics 

- **How Civil Wars Start**, _Barbara F. Walter_, 5 ⭐
- **How Westminster Works … and Why It Doesn’t**, _Ian Dunt_, 5 ⭐
- **Politics on the Edge**, _Rory Stewart_, 4 ⭐

## Economics

- **Brexitland**, _Maria Sobolewska and Robert Ford_, 5 ⭐
- **Economics: A User's Guide**, _Ha-Joon Chang_, 5 ⭐
- **Utopia for Realists**, _Rutger Bregman_, 3 ⭐
- **How to Be an Anticapitalist in the Twenty-First Century**, _Erik Olin Wright_, 3 ⭐
- **Doughnut Economics**, _Kate Raworth_, 4 ⭐
- **The Money Machine: How the City Works**, _Philip Coggan_, 3 ⭐

## History 

- **The Anarchy: The Relentless Rise of the East India Company**, _William Dalrymple_, 5 ⭐