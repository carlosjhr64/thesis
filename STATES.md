### [TABLE OF CONTENTS](CONTENTS.md)

## A. Energy Eigen-States of the Simple Harmonic Oscillator.

In [section three](QMSHO.md) of this paper,
I gave the energy eigen-states for the simple harmonic oscillator:

~~Yₙ[x] = AₙHₙ[y]e^(-y²)~~

~~y ≡ 2πmωx²/h~~

    Yₙ[x] = AₙHₙ[y]e^(-y²/2)   # A.1a
    y² ≡ 2πmωx²/h              # A.1b

> This is an uncaught error and it's probably in the UCSC copy.
> This is equations 7.46 and 7.59 in chapter 7 of Liboff's book.[³](REFERENCE.md)
> It's correct on my manuscript.  [Want a picture?](images/manuscript_500_888.png)
> I collected my notes on a three ring binder.
> It's called that because of it's three rings.
> Paper often came with three holds to clip through the rings of a three ring binder.

The constants `Aₙ` are given by

    Aₙ = (2ⁿn!π^½)^-½   # A.2a

This leads to the following result, which is used in section seven of this paper:

    A[n]≡Aₙ,
    A[n]/A[n-1] = (2n)^-½   # A.2b

> Note that I was not able to reproduce the n-1 subscript here,
> so introduce `A[n]≡Aₙ`.

`Hₙ[y]` are the Hermite polynomials.
There are many ways of expressing them, but here is one:

    Hₙ[y] = (-1)ⁿe^(y²)(Dᵧ)ⁿe^(y²)   # A.3

> Here I'm using `ᵧ` as subscript `y`, because I don't have the exact subscript.
> `Dᵧ` is the differential operator with respect to `y`.
> `(Dᵧ)ⁿ` is the nth derivative, `dⁿ/dyⁿ`, or `δⁿ/δyⁿ`.

The Hermite polynomial has the following recursion relations:

    (Dᵧ)H[n][y] = 2nH[n-1][y]             # A.4a
    H[n+1][y] = 2yH[n][y] - 2nH[n-1][y]   # A.4b

These were use for the analysis of the problem worked on this paper.
