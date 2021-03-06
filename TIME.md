### [CONTENTS](CONTENTS.md)

### 7.2 [Evaluation of `<y>`](Y.md)

## 7.3 Time Development

The time development of an energy eigen-state is given by

~~Yₙ[x,t] = Yₙ[x]e^(-iEₙt/h)~~

    Yₙ[x,t] = Yₙ[x]e^(-iEₙt/ħ)    # 7.16

where `Eₙ` is the energy of the eigen-state.

> Unfortunately, this is an uncaught error in my draft, so it may be in the UCSC copy.
> It's important to keep track of when we mean the
> [reduced Planck constant](http://en.wikipedia.org/wiki/Planck_constant),
> which is denoted as h-bar, `ħ=h/(2π)`.
> I'll need to keep track of how far this error propagates.
> In my [manuscript](images/ishbar.png), it's correct, so it looks to be a copy error.

For convenience, let the following be defined:

~~1ₙ = e^(-iEₙt/h)~~

    1ₙ = e^(-iEₙt/ħ)   # 7.17

> And I don't know why I didn't just use `Ιₙ` here.
> Must be very confusing for some that I'm using `1ₙ`.
> Sorry about that!

Then, since ~~Eₙ/h=ω(n+½)~~ `Eₙ/ħ=ω(n+½)`,

~~1ₙ† 1ₙ+ₘ = e^(iωmt) = cos[ωmt] + i sin[ωmt]~~

    1ₙ† 1ₙ+ₘ = e^(iωmt) = cos[ωmt] - i sin[ωmt]   # 7.18a

~~1ₙ† 1ₙ+ₘ = cₘ + isₘ~~

    1ₙ† 1ₙ+ₘ = cₘ - isₘ                           # 7.18b

> Seeing this at first (after 25 years) I admit I was a bit puzzled.
> So here's the derivation all explicitly laid out:

    1ₙ† 1ₙ+ₘ                         # Given
    e^(-iEₙt/h)† e^(-iEₙ+ₘt/h)       # By definition of 1ₙ
    e^(-iw(n+½)t)† e^(-iw(n+m+½)t)   # By substitution of Eₙ/ħ with ω(n+½)
    e^(-iwtu)† e^(-iwt(u+m))         # u:=n+½ (Let...)
    e^(iwtu) e^(-iwt(u+m))           # It's what complex conjugation does! :)
    e^(iwtu - iwt(u+m))              # A reason to really love e.
    e^(iwtu - iwtu - iwtm)           # Distribute
    e^(-iwtm)                        # iwtu-iwtu=0
    # or
    :Cosine[wtm] - i:Sine[wtm]
    # or
    cos[wtm] - i sin[wtm]
    # or
    cₘ - isₘ

> See also
> [Wolframalpha](http://www.wolframalpha.com/input/?i=conjugate%5Be%5E%28-i*n%29%5D+*+e%5E%28-i*%28n%2Bm%29%29).
> Ok, so caught an error, but I'm pretty sure it'll end up not mattering.
> it's just a phase shift.
> Keep an eye for that though as the same mistake is in my notes.
> `1ₙ†1ₙ=1` is still true:

    1ₙ† 1ₙ
    e^(-iEₙt/h)† e^(-iEₙt/h)
    e^(+iEₙt/h) e^(-iEₙt/h)
    e^0
    1

Using time development,

    <y> =                                                                      # 7.20
    Σₙ 1ₙ† pₙ†/2^½ (1ₙ+₁ pₙ+₁ [n+1]^½  +  1ₙ-₁ pₙ-₁ n^½)

~~`<y²>` = (nᵒ+½) + ½Σₙ 1ₙ† pₙ† (1ₙ-₂ pₙ-₁ [n(n-1)]^½  +  1ₙ+₂ pₙ+₂ [(n+1)(n+2)]^½)~~

    <y²> =                                                                     # 7.21
    (nᵒ+½) + ½Σₙ 1ₙ† pₙ† (1ₙ-₂ pₙ-₂ [n(n-1)]^½  +  1ₙ+₂ pₙ+₂ [(n+1)(n+2)]^½)

> And another copy error here.
> It's correct in my [manuscript](images/pn2.png).
> Looks like I was having trouble keeping track of h-bars in my manuscript too!
> I have a note to myself to check if I'm using h-bar correctly.

The evaluation of `<q²>` leads to almost the same result as `<y²>`, but differs by a sign.

~~`<q²>` = ½nᵒ + ½ - ½Σₙ 1ₙ† pₙ† (1ₙ-₂ pₙ-₂ [n(n-1)]^½  +  1ₙ+₂ pₙ+₂ [(n+1)(n+2)]^½)~~

    <q²> =                                                                      # 7.22
    (nᵒ + ½) - ½Σₙ 1ₙ† pₙ† (1ₙ-₂ pₙ-₂ [n(n-1)]^½  +  1ₙ+₂ pₙ+₂ [(n+1)(n+2)]^½)

> Another copy error.
> Checking my manuscript, 7.21 and 7.22 really only differs by a sign as described.
> And Looking ahead looks like I invoke difference of squares.

Assume that `<y>=0` at `t=0`, as is the case in `<n]y[n>` for all `n`.
Then the series for `<y>`, equation (7.20), vanishes term by term,
after perhaps a shifting of one of the indexes:

    pₙ†([n+1]^½ pₙ+₁) = -pₘ†(m^½ pₘ-₁)   # 7.23

This equation(7.23) will be one of the conditions on pₙ.
Furthermore, the evaluation of uncertainty is reduce to

    d[y] = <y²>  if t=0.   # 7.24

For the next step, notice that at `t=0`, `1ₙ=1`.
Thus, at `t=0`,

    <y²><q²> =                                                    # 7.25
    ¼(nᵒ+1)² - ¼(Σₙ pₙ†(pₙ-₂(n(n-1)))^½ + pₙ+₂((n+1)(n+2))^½)².

### 7.4 [The Related Programming Problem](RELATED.md)
