### [TABLE OF CONTENTS](CONTENTS.md)

### 2. [Review of the Simple Harmonic Oscillator in Classical Mechanics](REVIEW.md)

## 3. Energy Eigen-States and Eigen-Values of the Simple Harmonic Oscillator

The time independent Schrodinger equation for
the simple harmonic potential is given by[³⁴](REFERENCE.md)

    (-h²/(4πm)Dₓ² + kx²)Yₙ[x] = EₙYₙ[x]   # 3.1

where `h` is Plank's constant, `Eₙ` is the energy eigen-value, and `Yₙ[x]` is the energy eigen-state.
Solutions to this equation exist only for a discrete set of energy eigen-values.
The energy eigen-values are given by

~~Eₙ = (h/2π)(n+½)~~

    Eₙ = (ωh/2π)(n+½),   # 3.2

where n takes on non-negative integer values.

> On my draft I have penciled in a correction.
> I don't derive these.
> They're taken from a college text book.
> You can more quickly check these on
> [Wikipedia](http://en.wikipedia.org/wiki/Quantum_harmonic_oscillator).
> I probably used `h/(2π)` because I did not have available the `ℏ` character.
> I should have preferred:

    EₙYₙ[x] = (-ℏ²Dₓ²/m + kx²)Yₙ[x]
    Eₙ      = ωℏ(n+½)

> If we define ρ::ℏ²Dₓ² and mω²::k we get

    EₙYₙ[x] = (-ρ/m + mω²x²)Yₙ[x]
    Eₙ      = ωℏ(n+½)

The energy eigen-state solutions to this equation are given by

~~Yₙ[x] = AₙHₙ[y]e^(-y²),~~

~~y ≡ 2πmωx²/h,~~

    Yₙ[x] = AₙHₙ[y]e^(-y²/2),   # 3.3a
    y² ≡ 2πmωx²/h,              # 3.3b

where `Hₙ[y]` is the nth Hermite polynomial.

> These errors propated from typos that probably first occurred in the appendix A.
> Unfortunately, I think they were never caught and are in the UCSC copy.

For a full description of `Yₙ[x]`, please see [appendix A](STATES.md).
Since this equation is a linear differential equation,
any arbitrary sum of its eigen-states will also be a solution:

    Y[x] = Σₙ pₙYₙ[x]   # 3.4

In this paper, I will mostly use the Dirac notation, but
I will switch notations whenever it is convenient.
The manipulations of the Dirac notation symbols easily incorporate
the algebraic structure of Quantum Mechanics.

The following defines the Dirac notation:[³](REFERENCE.md)

    <n][m> ≡ ∫ Yₙ†[x]Yₘ[x]   # 3.5a
    <n][am> = a<n][m>        # 3.5b
    <an][m> = a†<n][m>       # 3.5c
    <n][m>† = <m][n>         # 3.5d
    <n+m] = <n] + <m]        # 3.5e.i

> One might see Dirac notation written like `<n|m>` and `<n|+<m|` elsewhere.
> Working with the typewriter I was thinking very mechanically about these symbols.
> It just seemed to me that I should have distinct "open" and "close" symbols.
> [Wikipedia](http://en.wikipedia.org/wiki/List_of_computer_algebra_systems)
> shows algebraic software available as early as the 1960s, but
> I don't remember even being aware of them.

To avoid ambiguity between the numbers n and m, and the states they represent,
I add the following:

    <(n+m)] = Yₙ+ₘ[x]   # 3.5e.ii

> In the Dirac notation, `n` and `m` are enumeration labels.
> You don't add state 3 and state 5 to get state 8, for example.
> I had to look these up again as it's not clear to me now what `<n+m]` is.
> In *Introductory Quantum Mechanics* by Richard L. Liboff, 1st edition, chapter 4, page 93:

    (4.19)   <ψ|φ> = ∫ ψ*(x)φ(x) dx < ∞
    (4.20)   ∫ ψ*φdx < ∞
    (4.21)   <ψ|αφ> = α<ψ|φ>
    (4.22)   <αψ|φ> = α*<ψ|φ>
    (4.23)   <ψ|φ>* = <φ|ψ>
    (4.24)   <ψ+φ| = <ψ| + <φ|
    (4.25)   ∫(ψ₁+ψ₂)*(φ₁+φ₂)dx
             = <ψ₁+ψ₂|φ₁+φ₂>=(<ψ₁|+<ψ₂|)(|φ₁>+|φ₂>)
             = <ψ₁|φ₁>+<ψ₁|φ₂>+<ψ₂|φ₁>+<ψ₂|φ₂>

> I think (4.25) makes clearer what <ψ+φ| means.
> Can you see why I chose to use `†` instead of `*`?
> Anyways, I don't think the issue with `#3.5e.i` and `(4.24)` ever comes up in my proof later.

Placing two indices side by side will indicate that
the sum overall of the of the indices is to be evaluated, for example:

    <Y][n><n][Y> = 1   # 3.6a

> Is it "over all" or "overall?"

Otherwise only the product is to be evaluated, as when
determining the norm of an eigen-state component of a state `[Y>`:

    <n][Y><Y][n> = ∫ Y†[x]Y[x] dx   # 3.6b

Due to the orthonormallity of eigenstates,

    <m][n> = 0 for n ≠ m   # 3.7a

and

    <n][n> = 1.            # 3.7b

Then, the superposition principle is stated as

    [Y> = [n><n][Y>   # 3.8
    pₙ = <n][Y>.

### 4. [Measure of Uncertainty](UNCERTAINTY.md)
