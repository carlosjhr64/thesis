[CONTENTS](CONTENTS.md)

# The Full Monty

> This section was not in the original thesis.
> I got a bit carried away on this "Full Monty", lost focus, went off on tangental issues...
> So I moved most of it to a "[Scratch Work](SCRATCH.md)" section.

##<a name="85"></a> Optimization problem
The [Optimization problem](http://en.wikipedia.org/wiki/Optimization_problem)
to be solved:

    Minimize:   ΔxΔp
    Subject to: ⧼Ψₒ|𝐇|Ψₒ⧽ = Eₒ

This will be for the quantum mechanical simple harmonic oscillator
with energy [Eₒ](SCRATCH.md#k5Y),
state function [Ψₒ](SCRATCH.md#lHR),
Hamiltonian(energy) operator [𝐇](SCRATCH.md#bdY),
position operator [𝐱](SCRATCH.md#0bH), and
momentum operator [𝐩](SCRATCH.md#w6M).
I will show that the product of the variance of position [Δ²x](SCRATCH.md#oY8)
and momentum [Δ²p](SCRATCH.md#k94) is the minimum when the state Ψₒ
is composed of a Poisson distribution [𝑃ₙ](SCRATCH.md#o0H) of energy states, and
that the minimum is that set by the uncertainty principle
due to the commutator relationship between 𝐱 and 𝐩, [&#91;𝐱,𝐩&#92;](SCRATCH.md#bST).

> TODO: section on quantum number n.

Noting that [Eₙ](SCRATCH.md#2Xh) goes as the quantum number n, and
using the definitions of Δx and Δp, I then have:

    Minimize:   √ (⧼x²⧽-⧼x⧽²)(⧼p²⧽-⧼p⧽²)
    Subject to: ⧼n⧽ = ñ

where [ñ](SCRATCH.md#Ojo) is the average quantum number.

It would not be to hard to argue (TODO: demonstrate this) that
by symmetry (⧼x²⧽-⧼x⧽²)=(⧼p²⧽-⧼p⧽²) and also that I can set ⧼x⧽=0.
Then the problem is:

    Minimize:   ⧼x²⧽
    Subject to: ⧼n⧽=ñ, ⧼x⧽=0, ⧼x²⧽=⧼p²⧽-⧼p⧽²

I suspect the extra conditions might be satisfied "for free".
Let's see how that goes:

    Min: ⧼x²⧽
    Sub: ⧼n⧽ = ñ   # Ignoring the rest of the constraints for now.

## ℒ
[Lagrange multiplier](http://en.wikipedia.org/wiki/Lagrange_multiplier):

    ℒ = ⧼x²⧽ + λ(⧼n⧽-ñ)

    𝒟ₓℒ = 𝒟ₓ⧼x²⧽ + λ𝒟ₓ⧼n⧽ - λ𝒟ₓñ
    𝒟ₓℒ = 𝒟ₓ⧼x²⧽ + λ𝒟ₓ⧼n⧽   # ñ is just a constant and goes away.

## 𝒟 ⧼n⧽=0
Consider ⧼n⧽.
Just want to prove ⧼n⧽ really is a simple constant:

    𝒟ₓ⧼n⧽
    𝒟 ⧼n⧽                           # Change of variable, ξ.
    𝒟 ⧼Ψₒ|ₙ⧽⧼ₙ|n|ₘ⧽⧼ₘ|Ψₒ⧽           # Expanding out ⧼n⧽.
    𝒟 ⨋ (𝑝ₙΨₙ)*n𝑝ₘΨₘ                # ⨋ is an integral over ξ of a sum over n and m!
    𝒟 ⨋ (𝑝Ψ*)n𝑝ₘΨₘ                  # Context ₙ for brevity.
    𝒟 ⨋ 𝑝Ψn𝑝ₘΨₘ                     # There is nothing to conjugate in Ψₙ.
    𝒟 ⨋ n𝑝𝑝ₘΨΨₘ                     # Rearrangement.
    ⨋ n𝑝𝑝ₘ𝒟[ΨΨₘ]                    # 𝒟 only acts on Ψ.
    ⨋ n𝑝𝑝ₘ(𝒟[Ψ]Ψₘ + Ψ𝒟[Ψₘ])         # Product rule.
    ⨋{n𝑝𝑝ₘ𝒟[Ψ]Ψₘ} + ⨋{n𝑝𝑝ₘΨ𝒟[Ψₘ]}   # Separate sums.

See the derivation of [𝒟 Ψ](SCRATCH.md#W3A).  Then proceed:

    ⨋{n𝑝𝑝ₘ𝒟[Ψ]Ψₘ} + ⨋{n𝑝𝑝ₘΨ𝒟[Ψₘ]}                               # Continue from above.
    ⨋{n𝑝𝑝ₘ(√½(√ŉ↧Ψ↓-√n↥Ψ↑))Ψₘ} + ⨋{n𝑝𝑝ₘΨ(√½(√ʼm↧Ψₘ↓-√m↥Ψₘ↑))}   # Subtitution of 𝒟 Ψ.
    √½(⨋{n𝑝𝑝ₘ(√ŉ↧Ψ↓-√n↥Ψ↑)Ψₘ} + ⨋{n𝑝𝑝ₘΨ(√ʼm↧Ψₘ↓-√m↥Ψₘ↑)})       # Take out √½.

That 𝒟 ⧼n⧽ vanishes should not be a property of 𝑝.
I proceed as if I don't know what 𝑝 is:

    √½(⨋{n𝑝𝑝ₘ(√ŉ↧Ψ↓-√n↥Ψ↑)Ψₘ} + ⨋{n𝑝𝑝ₘΨ(√ʼm↧Ψₘ↓-√m↥Ψₘ↑)})         # Continue from above.
    √½(⨋{n𝑝𝑝ₘ(√ŉ↧Ψ↓Ψₘ-√n↥Ψ↑Ψₘ)} + ⨋{n𝑝𝑝ₘ(√ʼm↧ΨΨₘ↓-√m↥ΨΨₘ↑)})      # Distribute Ψ.
    √½(⨋{n𝑝𝑝ₘ√ŉ↧Ψ↓Ψₘ-n𝑝𝑝ₘ√n↥Ψ↑Ψₘ} + ⨋{n𝑝𝑝ₘ√ʼm↧ΨΨₘ↓-n𝑝𝑝ₘ√m↥ΨΨₘ↑})  # Distribute n𝑝𝑝ₘ.
    √½(⨋{n√ŉ↧𝑝𝑝ₘΨ↓Ψₘ-n√n↥𝑝𝑝ₘΨ↑Ψₘ} + ⨋{n√ʼm↧𝑝𝑝ₘΨΨₘ↓-n√m↥𝑝𝑝ₘΨΨₘ↑})  # Rearrangement.
    √½(⨋{n√n𝑝𝑝ₘΨ↓Ψₘ-n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓-n√[m+1]𝑝𝑝ₘΨΨₘ↑}) # Evaluate "factorals".

There are positive and negative terms very much like eachother.
Going to match them up:

    √½(⨋{n√n𝑝𝑝ₘΨ↓Ψₘ-n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓-n√[m+1]𝑝𝑝ₘΨΨₘ↑})       # Continue from above.
    √½(⨋{n√n𝑝𝑝ₘΨ↓Ψₘ}-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓}-⨋{n√[m+1]𝑝𝑝ₘΨΨₘ↑}) # Separate sums.
    √½(⨋{n√n𝑝𝑝ₘΨ↓Ψₘ}-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓}-⨋{n√m𝑝𝑝ₘ↓ΨΨₘ})     # ↓ m, 4th ⨋.
    √½(⨋{n√n𝑝𝑝ₘΨ↓Ψₘ}-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓}-⨋{n√n𝑝𝑝↓𝛿})        # ⟂ΨΨ=𝛿, 4th ⨋.
    √½(⨋{n√n𝑝𝑝ₘ↓Ψ↓Ψₘ↓}-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓}-⨋{n√n𝑝𝑝↓𝛿})      # ↓ m, 1st ⨋.
    √½(⨋{n√n𝑝𝑝↓𝛿}-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓}-⨋{n√n𝑝𝑝↓𝛿})           # ⟂ΨΨ=𝛿, 1st ⨋.
    √½(-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√m𝑝𝑝ₘΨΨₘ↓})                                # Cancellation.
    √½(-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√[m+1]𝑝𝑝ₘ↑ΨΨₘ})                            # ↑ m, 2nd ⨋.
    √½(-⨋{n√[n+1]𝑝𝑝ₘΨ↑Ψₘ}+⨋{n√[n+1]𝑝𝑝↑𝛿})                               # ⟂ΨΨ=𝛿, 2nd ⨋.
    √½(-⨋{n√[n+1]𝑝𝑝ₘ↑Ψ↑Ψₘ↑}+⨋{n√[n+1]𝑝𝑝↑𝛿})                             # ↑ m, 1st ⨋.
    √½(-⨋{n√[n+1]𝑝𝑝↑𝛿}+⨋{n√[n+1]𝑝𝑝↑𝛿})                                  # ⟂ΨΨ=𝛿, 1st ⨋.
    0                                                                   # Cancellation.

I should point out that these are sums over Integers,
not just natural numbers.
But there are no negative quantum numbers for the harmonic oscillator.
That is, for quantum numbers less than 0, the states are zero!
So there are no dangling terms with [∑u↑](SCRATCH.md#Uf9) or [∑u↓](SCRATCH.md#blg).

## 𝒟ₓ⧼x²⧽
Consider ⧼x²⧽.
This should give the properties of an optimun distribution:

    𝒟ₓ⧼𝐱²⧽
    𝒟ₓ⧼x²⧽                        # x is the position operator.
    𝒟ₓ⧼ξ²⧽                        # Change of variable, dimensionless ξ.
    𝒟ₓ ⧼Ψₒ|ₙ⧽⧼ₙ|ξ²|ₘ⧽⧼ₘ|Ψₒ⧽       # Expanding out ⧼ξ²⧽.
    𝒟 ⨋ (𝑝ₙΨₙ)*ξ²𝑝ₘΨₘ             # ⨋ is an integral over ξ of a sum over n and m!
    𝒟 ⨋ (𝑝Ψ)*ξ²𝑝ₘΨₘ               # Implicit n, explicit m.
    𝒟 ⨋ 𝑝Ψξ²𝑝ₘΨₘ                  # Nothing to conjugate.
    𝒟 ⨋ 𝑝𝑝ₘξ²ΨΨₘ                  # Rearrange.
    𝒟 ⨋ 𝑝𝑝ₘξΨξΨₘ                  # Pair up ξΨ.
    ⨋ 𝑝𝑝ₘ𝒟[ξΨξΨₘ]                 # 𝒟 only acts on ξΨ.
    ⨋ 𝑝𝑝ₘ𝒟[(ξΨ)(ξΨₘ)]             # Going to apply product rule this way.
    ⨋ 𝑝𝑝ₘ(𝒟[ξΨ]ξΨₘ+ξΨ𝒟[ξΨₘ])      # Product rule.
    ⨋ 𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ+𝑝𝑝ₘξΨ𝒟[ξΨₘ]     # Distribute 𝑝𝑝ₘ.
    ⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ}+⨋{𝑝𝑝ₘξΨ𝒟[ξΨₘ]} # Separate sums.
    ⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ}+⨋{𝑝ₘ𝑝ξΨₘ𝒟[ξΨ]} # Switch n and m in 2nd ⨋.
    ⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ}+⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ} # Rearange.
    2⨋ 𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ                # The two ⨋s are the same.

See the derivation of [ξΨ](SCRATCH.md#4V4). Then proceed:

    2⨋ 𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ                # Continue from above.
    2⨋ 𝑝𝑝ₘ(𝒟[ξ]Ψ+ξ𝒟[Ψ])ξΨₘ        # Product rule.
    2⨋ 𝑝𝑝ₘ(Ψ+ξ𝒟[Ψ])ξΨₘ            # 𝒟 ξ = 1.
    2⨋ 𝑝𝑝ₘ(ΨξΨₘ+ξ𝒟[Ψ]ξΨₘ)         # Distribute ξΨₘ.
    2⨋ 𝑝𝑝ₘΨξΨₘ+𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ        # Distribute 𝑝𝑝ₘ.
    2⨋{𝑝𝑝ₘΨξΨₘ}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}   # Separate sums.
    2⨋{ξ𝑝𝑝ₘΨΨₘ}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}   # Rearrage in 1st ⨋.
    2⨋{ξ𝑝𝑝ₘ𝛿}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}     # ⟂ΨΨ=𝛿.
    2∫{⅀{ξ𝑝𝑝ₘ𝛿}}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}  # Wuts really goin on in 1st ⨋.
    2∫{ξ⅀{𝑝𝑝ₘ𝛿}}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}  # Take ξ out off ⅀(sum over n and m).
    2∫{ξ∑𝑃} + 2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}     # ⅀ 𝑝𝑝ₘ𝛿 = ∑𝑃
    2∫{ξ} + 2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}       # Sum of a distribution, ∑𝑃 = 1.
    2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}               # ∫ξ=0
    2⨋{𝑝𝑝ₘξ(√½(√ŉ↧Ψ↓-√n↥Ψ↑))ξΨₘ}  # Substitute in 𝒟 Ψ.
    √2⨋{𝑝𝑝ₘξ(√ŉ↧Ψ↓-√n↥Ψ↑)ξΨₘ}     # √½(2)=√2
    √2⨋{(√ŉ↧ξ𝑝Ψ↓-√n↥ξ𝑝Ψ↑)ξ𝑝ₘΨₘ}   # Pair up ξ𝑝Ψ(distribute).
    √2⨋{(√ŉ↧ξ𝑝Ψ↓ξ𝑝ₘΨₘ-√n↥ξ𝑝Ψ↑ξ𝑝ₘΨₘ)}
    √2(⨋{(√ŉ↧ξ𝑝Ψ↓ξ𝑝ₘΨₘ}-⨋{√n↥ξ𝑝Ψ↑ξ𝑝ₘΨₘ)})
    √2(⨋{(√ŉ↧ξ²𝑝Ψ↓𝑝ₘΨₘ}-⨋{√n↥ξ²𝑝Ψ↑𝑝ₘΨₘ)})
    √2(⨋{(ξ²√ŉ↧𝑝Ψ↓𝑝ₘΨₘ}-⨋{ξ²√n↥𝑝Ψ↑𝑝ₘΨₘ)})
    √2(⨋{ξ²√ŉ↧√[ñn↧]𝑝↓Ψ↓𝑝ₘΨₘ}-⨋{ξ²√n↥√[ʼñn↥]𝑝↑Ψ↑𝑝ₘΨₘ}) # 𝑝 = √(m,ʼñ)↥𝑝↑ = √(m,ʼñ)↧𝑝↓
    √2(⨋{ξ²ŉ↧√ñ𝑝↓Ψ↓𝑝ₘΨₘ}-⨋{ξ²n↥√ʼñ𝑝↑Ψ↑𝑝ₘΨₘ})
    √2(⨋{ξ²ŉ↧√ñ𝑝↓Ψ↓𝑝↓Ψ↓}-⨋{ξ²n↥√ʼñ𝑝↑Ψ↑𝑝↑Ψ↑})   # Set m to match.
    √2(⨋{ξ²ŉ↧√ñ𝑃↓𝛿}-⨋{ξ²n↥√ʼñ𝑃↑𝛿})
    √2(⨋{ξ²n√ñ𝑃↓𝛿}-⨋{ξ²(n+1)√ʼñ𝑃↑𝛿})   # Evaluate "factorals"

    n√ñ𝑃↓ = (n+1)√ʼñ𝑃↑  # B.4 ???
    n√ñ𝑃↓ = (n+1)𝑃↑/√ñ
    n√ñ𝑃 = (n+1)𝑃↑²/√ñ
    n√ñ𝑃 = (n+1)𝑃ₙ₊₂/√ñ
    n𝑃 = (n+1)𝑃ₙ₊₂/ñ
    𝑃 = (n+1)𝑃ₙ₊₂/(nñ)
    ñ𝑃 = (n+1)𝑃ₙ₊₂/n

> WOW! OK, I think I now understand what I did 25 years ago.
> I need to follow the original thesis more closely!  LOL.
