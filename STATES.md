### [TABLE OF CONTENTS](CONTENTS.md)

## A. Energy Eigen-States of the Simple Harmonic Oscillator.

In [section three](QMSHO.md) of this paper,
I gave the energy eigen-states for the simple harmonic oscillator:

    Yₙ[x] = AₙHₙ[y]e^(y²)   # A.1a
    y ≡ 2πmωx²/h            # A.1b

The constants `Aₙ` are given by

    Aₙ = (2ⁿn!π^½)^-½   # A.2a

This leads to the following result, which is used in section seven of this paper:

    A[n]≡Aₙ,
    A[n]/A[n-1] = (2n)^-½   # A.2b

> Note that I was not able to reproduce the n-1 subscript here,
> so introduce `A[n]≡Aₙ`.

`Hₙ[y]` are the Hermite polynomials.
There are many ways of expressing them, but here is one:

    Hₙ[y] = (-1)ⁿe^(y²)(D[y])e^(y²)   # A.3

> `D[y]` is D subscript y, but I do not have the subscript y.
> TODO: What is `D`???
> I personally don't need to re-derive the entire QM system just work on my problem, but
> it be nice if I could remember what's going on here.

The Hermite polynomial has the following recursion relations:

    (D[y])H[n][y] = 2nH[n-1][y]           # A.4a
    H[n+1][y] = 2yH[n][y] - 2nH[n-1][y]   # A.4b

These were use for the analysis of the problem worked on this paper.

> OK, so this page is a complete mistery to me now.
> I'll probably be reviewing this for while before moving on.
