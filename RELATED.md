### [CONTENTS](CONTENTS.md)

### 7.3 [Time Development](TIME.md)
...

    <y²><q²> =                                                    # 7.25
    ¼(nᵒ+1)² - ¼(Σₙ pₙ†(pₙ-₂(n(n-1)))^½ + pₙ+₂((n+1)(n+2))^½)².


## 7.4 The Related Programming Problem

To minimize this quantity(7.25), I want to

    max Σₙpₙ†(pₙ-₂(n(n-1))^½ + pₙ+₂((n+1)(n+2))^½)^²   # 7.26a
    sub Pₙ ≡ pₙ†pₙ ≤ 1                                 # 7.26b
    Σₙ Pₙ = 1                                          # 7.26c
    Σₙ nPₙ = nᵒ                                        # 7.26d

This is a quadratic programming problem in pₙ.

The Karush-Kuhn-Tucker (KKT) conditions for constrained optimization[²](REFERENCE.md)
states that there exists some `u` such that the following for optimum pₙ holds:

    (a) pₙ+₂†[(n+1)(n+2)]^½ + pₘ-₂[m(m-1)]^½ ≤ 2upₙ             # 7.27
    (b) pₙ†(pₙ+₂[(n+1)(n+2)]^½)+pₘ†(pₘ-₂[m(m-1)]^½)-2upₙ†pₙ)=0

> TODO: There's a problem with (b), I think I know what I meant to write, need to check...

    (c) pₙ†pₙ ≤ 1
    (d) u(Σₙ pₙ†pₙ - 1) = 0
    (e) pₙ ≠ 0
    (f) u ≠ 0

Following a precedence set in (7.23), `m` is used to allow for a shift in one of the indexes.
Let `u≡nᵒ`.
These conditions can be reinterpreted as follows:

    (a&b) pₙ†(pₙ+₂[(n+1)(n+2)]^½) + pₘ†(pₘ-₂[m(m-1)]^½) = 2nᵒpₙ†pₙ   # 7.28
    (c&e) 0 ≤ pₙ†pₙ ≤ 1
    (d) Σₙ pₙ†pₙ = 1
    (f) nᵒ ≥ 0

Conditions (c) through (e) implies a distribubtion function.
Conditions (a&b) and equation (7.23) are satisfied by

    pₙ = [-i]ⁿe^[-nᵒ/2][nᵒ]^[½n]/[n!]^½   # 7.29

See [appendix B](PROPERTIES.md) for demonstration.
Therefore, `Pₙ=pₙ†pₙ` is a Poisson distribution for values of `n` with average value `nᵒ`:

    Pₙ = pₙ†pₙ = e^[-nᵒ](nᵒ)^n/n!   # 7.30

> The point here, in case anybody missed it, is that the Poisson distribution is the solution to this problem!
> Honestly, I can't say I've followed everything up to here.
> But that's what this section is saying.
> Now, lets evaluate this solution.

### 7.5 [Results](RESULTS.md)
