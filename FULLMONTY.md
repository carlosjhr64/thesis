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
is composed of a Poisson distribution [𝑃ₙ](SCRATCH.md#o0H), and
that the minimum is that set by the uncertainty principle
due to the commutator relationship between 𝐱 and 𝐩, [&#91;𝐱,𝐩&#92;](SCRATCH.md#bST).

Noting that Eₙ goes as the quantum number n, and
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
    𝒟 ⧼n⧽                           # Change of varible, ξ.
    𝒟 ⧼Ψₒ|ₙ⧽⧼ₙ|n|ₘ⧽⧼ₘ|Ψₒ⧽           # Expanding out ⧼n⧽.
    𝒟 ⨋ 𝑝ₙΨₙ*n𝑝ₘΨₘ                  # ⨋ is an integral over x of a sum over n and m!
    𝒟 ⨋ 𝑝Ψ*n𝑝ₘΨₘ                    # Context ₙ for brevity.
    𝒟 ⨋ 𝑝Ψn𝑝ₘΨₘ                     # There nothing to conjugate in Ψₙ.
    𝒟 ⨋ n𝑝𝑝ₘΨΨₘ                     # Rearrangement.
    ⨋ n𝑝𝑝ₘ𝒟[ΨΨₘ]                    # 𝒟 only acts on Ψ.
    ⨋ n𝑝𝑝ₘ(𝒟[Ψ]Ψₘ + Ψ𝒟[Ψₘ])         # Product rule.
    ⨋[n𝑝𝑝ₘ𝒟[Ψ]Ψₘ] + ⨋[n𝑝𝑝ₘΨ𝒟[Ψₘ]]   # Separate sums.
    ⨋[n𝑝𝑝ₘ𝒟[Ψ]Ψₘ] + ⨋[m𝑝ₘ𝑝Ψₘ𝒟[Ψ]]   # Switch n and m on second ⨋.

See the derivation of [𝒟 Ψ](SCRATCH.md#W3A).  Then proceed:

    ⨋[n𝑝𝑝ₘ𝒟[Ψ]Ψₘ] + ⨋[m𝑝ₘ𝑝Ψₘ𝒟[Ψ]]                             # Continue from above.
    ⨋[n𝑝𝑝ₘ(√½(√ŉ↧Ψ↓-√n↥Ψ↑))Ψₘ] + ⨋[m𝑝ₘ𝑝Ψₘ(√½(√ŉ↧Ψ↓-√n↥Ψ↑))]   # Subtitution of 𝒟 Ψ.
    √½(⨋[n𝑝𝑝ₘ(√ŉ↧Ψ↓-√n↥Ψ↑)Ψₘ] + ⨋[m𝑝ₘ𝑝Ψₘ(√ŉ↧Ψ↓-√n↥Ψ↑)])       # Take out √½.

That 𝒟 ⧼n⧽ vanishes should not be a property of 𝑝.
I proceed as if I don't know what 𝑝 is:

    √½(⨋[n𝑝𝑝ₘ(√ŉ↧Ψ↓-√n↥Ψ↑)Ψₘ] + ⨋[m𝑝ₘ𝑝Ψₘ(√ŉ↧Ψ↓-√n↥Ψ↑)])           # Continue from above.
    √½(⨋[n𝑝𝑝ₘ(√ŉ↧Ψ↓Ψₘ-√n↥Ψ↑Ψₘ)] + ⨋[m𝑝ₘ𝑝(√ŉ↧ΨₘΨ↓-√n↥ΨₘΨ↑)])       # Distribute Ψₘ.
    √½(⨋[n𝑝𝑝ₘ√ŉ↧Ψ↓Ψₘ-n𝑝𝑝ₘ√n↥Ψ↑Ψₘ] + ⨋[m𝑝ₘ𝑝√ŉ↧ΨₘΨ↓-m𝑝ₘ𝑝√n↥ΨₘΨ↑])   # Distribute n𝑝𝑝ₘ and m𝑝ₘ𝑝.
    √½(⨋[n√ŉ↧𝑝𝑝ₘΨ↓Ψₘ-n√n↥𝑝𝑝ₘΨ↑Ψₘ] + ⨋[m√ŉ↧𝑝ₘ𝑝ΨₘΨ↓-m√n↥𝑝ₘ𝑝ΨₘΨ↑])   # Rearrangement.
    √½(⨋[n√n𝑝𝑝ₘΨ↓Ψₘ-n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[m√n𝑝ₘ𝑝ΨₘΨ↓-m√[n+1]𝑝ₘ𝑝ΨₘΨ↑]) # Evaluate "factorals".
    √½(⨋[n√n𝑝𝑝ₘΨ↓Ψₘ-n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓-n√[m+1]𝑝𝑝ₘΨΨₘ↑]) # Switch back n and m on second ⨋.

There are positive and negative terms very much like eachother.
Going to try to match them up:
Although I'm doing separate sums,
restoring the original labels n and m to what it was in the original series
should make any cancellations clearer.

    √½(⨋[n√n𝑝𝑝ₘΨ↓Ψₘ-n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓-n√[m+1]𝑝𝑝ₘΨΨₘ↑])       # Continue from above.
    √½(⨋[n√n𝑝𝑝ₘΨ↓Ψₘ]-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓]-⨋[n√[m+1]𝑝𝑝ₘΨΨₘ↑]) # Separate sums.
    √½(⨋[n√n𝑝𝑝ₘΨ↓Ψₘ]-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓]-⨋[n√m𝑝𝑝ₘ↓ΨΨₘ])     # ↓ m, 4th ⨋.
    √½(⨋[n√n𝑝𝑝ₘΨ↓Ψₘ]-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓]-⨋[n√n𝑝𝑝↓])         # ⟂ΨΨ=1, 4th ⨋.
    √½(⨋[n√n𝑝𝑝ₘ↓Ψ↓Ψₘ↓]-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓]-⨋[n√n𝑝𝑝↓])       # ↓ m, 1st ⨋.
    √½(⨋[n√n𝑝𝑝↓]-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓]-⨋[n√n𝑝𝑝↓])             # ⟂ΨΨ=1, 1st ⨋.
    √½(-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√m𝑝𝑝ₘΨΨₘ↓])                                # Cancellation.
    √½(-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√[m+1]𝑝𝑝ₘ↑ΨΨₘ])                            # ↑ m, 2nd ⨋.
    √½(-⨋[n√[n+1]𝑝𝑝ₘΨ↑Ψₘ]+⨋[n√[n+1]𝑝𝑝↑])                                # ⟂ΨΨ=1, 2nd ⨋.
    √½(-⨋[n√[n+1]𝑝𝑝ₘ↑Ψ↑Ψₘ↑]+⨋[n√[n+1]𝑝𝑝↑])                              # ↑ m, 1st ⨋.
    √½(-⨋[n√[n+1]𝑝𝑝↑]+⨋[n√[n+1]𝑝𝑝↑])                                    # ⟂ΨΨ=1, 1st ⨋.
    0                                                                   # Cancellation.

## 𝒟ₓ⧼x²⧽
Consider ⧼x²⧽.
This should give the properties of an optimun distribution:

    𝒟ₓ⧼x²⧽
    # TODO...
