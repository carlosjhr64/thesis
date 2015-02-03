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

    p[n] ≡ pₙ
    p[n]†p[n-1] = -i([nᵒ]^½/n^½)P[n-1]    # B.3a
    p[n]†p[n+1] = i([nᵒ]^½/[n+1]^½)P[n]   # B.3b

> Because of my need to resort to `p[n]≡pₙ` here,
> it was impossible to unambiguously write the following B.4 expression as in the orignal thesis.

One of the conditions for optimum ~~pn~~ `pₙ` is

    p[n] ≡ pₙ
    p[n]† √(n+1) p[n+1]  =  -p[m]† √(m) p[m-1]   # B.4

which is satisfied with m=n+1
(perhaps obvious from the beginning).

> Wut!?  What was obvious from the beginning?
> TODO: This seems to be an important point which I don't get at the moment.

The other condition on `pₙ` is

    p[n]† p[n+2] √((n+1)(n+2))  +  p[m]† p[m-2] √(m(m+1))  =  2nᵒ p[n]† p[n]   # B.5

But

    p[n]† p[n+2] = -[nᵒ]^(n+1) e^[-nᵒ] / (n! [(n+1)(n+2)]^½)   # B.6a
    = -nᵒ P[n] / √((n+1)(n+2)),

and

    p[n]† p[n-2] = -nᵒ P[n-2] / √(n(n+1))   # B.6b

Thus in condition B.5, m=n+2.

> At the moment I can explain that we need to be able to say something about what
> `p[n]` and `p[n+1]`(and maybe `p[n+2]`) look like for the optimal distribution
> in order for the induction argument to work.
> I believe this part is where my original work begins, but
> I don't know where I'm getting these relations from.
> Maybe when I review the KKT conditions next, it'll be clearer.
