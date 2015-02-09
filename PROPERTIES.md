### [TABLE OF CONTENTS](CONTENTS.md)

## B. Properties of Optimun pₙ

It is assumed in section seven that pₙ is given by

    pₙ = [-i]ⁿe^[-½nᵒ][nᵒ]^[½n]/[n!]^½   # B.1

> I was obviously worried about how one might misread B.1.
> And maybe I did not have a square root symbol.
> If agreed that `½` and `-` binds strongly to the right token, and
> `!` binds strongly to the left as normally, and
> that `nᵒ` is a consider a single token, then
> this less cluttered expression is equivalent:
>
> `pₙ = -iⁿ e^-½nᵒ nᵒ^½n / √n!`

The `[-i]ⁿ` factor cycles among the four elements of the set `{1, -i, -1, i}`.
The distribution of energy eigen-states is given by

    Pₙ = pₙ†pₙ = e^-nᵒ[nᵒ]ⁿ/n!   # B.2

which is a Poisson distribution.

> You can read more about the Poisson distrubtion in
> [Wikipedia](http://en.wikipedia.org/wiki/Poisson_distribution).
> `nᵒ` is the expected quantum number... basically relates to the average energy.
> By expected quantum number, I mean any Real positive number,
> a (Real) weigted average of quantum numbers,
> it's not in itself a quantum number (a Natural number).
> I'm talking to Physicist here, right?
> Me!? Oh, no, no no no... LOL

The following properties hold:

    pₙ†pₙ-₁ = -i([nᵒ]^½/n^½)Pₙ-₁    # B.3a
    pₙ†pₙ+₁ = i([nᵒ]^½/[n+1]^½)Pₙ   # B.3b

One of the conditions for optimum ~~pn~~ `pₙ` is

    pₙ† √[n+1] pₙ+₁  =  -pₘ† √[m] pₘ-₁   # B.4

which is satisfied with m=n+1
(perhaps obvious from the beginning).

> Wut!?  What was obvious from the beginning?
> TODO: This seems to be an important point which I don't get at the moment.

The other condition on `pₙ` is

    pₙ† pₙ+₂ [(n+1)(n+2)]^½  +  pₘ† pₘ-₂ [m(m+1)]^½  =  2nᵒ pₙ† pₙ   # B.5

But

    pₙ† pₙ+₂ = -[nᵒ]^(n+1) e^[-nᵒ] / (n! [(n+1)(n+2)]^½)   # B.6a
    = -nᵒPₙ/[(n+1)(n+2)]^½,

and

    pₙ† pₙ-₂ = -nᵒPₙ-₂/[n(n+1)]^½   # B.6b

Thus in condition B.5, m=n+2.

> At the moment I can explain that we need to be able to say something about what
> `pₙ` and `pₙ+₁`(and maybe `pₙ+₂`) look like for the optimal distribution
> in order for the induction argument to work.
> I believe this part is where my original work begins, but
> I don't know where I'm getting these relations from.
> Maybe when I review the KKT conditions next, it'll be clearer.
