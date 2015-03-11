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
due to the commutator relationship between 𝐱 and 𝐩, [[𝐱,𝐩]](SCRATCH.md#bST).


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

    # Ignoring the rest for now.
    Min: ⧼x²⧽
    Sub: ⧼n⧽ = ñ

    ℒ = ⧼x²⧽ + λ(⧼n⧽-ñ)

    𝒟ₓℒ = 𝒟ₓ⧼x²⧽ + λ𝒟ₓ⧼n⧽ - λ𝒟ₓñ
    𝒟ₓℒ = 𝒟ₓ⧼x²⧽ + λ𝒟ₓ⧼n⧽   # ñ is just a constant and goes away.

    # Just want to prove ⧼n⧽ really is a simple constant.
    𝒟ₓ⧼n⧽                   
    𝒟ₓ ⧼Ψₒ|ₙ⧽⧼ₙ|n|ₘ⧽⧼ₘ|Ψₒ⧽
    𝒟 ΣΣ (𝑝ₙ𝐴ₙℋₙ𝒢)* n 𝑝ₘ𝐴ₘℋₘ𝒢   # Change of variable to ξ.
    𝒟 ΣΣ n𝒢𝒢 𝑝ₙ𝐴ₙℋₙ 𝑝ₘ𝐴ₘℋₘ      # Rearranged and recognized it's all Real.
    𝒟 ΣΣ nℊ 𝑝ₙ𝐴ₙℋₙ 𝑝ₘ𝐴ₘℋₘ
    𝒟 Σ{nℊ 𝑝𝐴ℋ}×Σ{𝑝𝐴ℋ}
    # TODO: define ⋅ operator
    𝒟 ({nℊ}⋅{𝑝𝐴ℋ})×Σ{𝑝𝐴ℋ}
    𝒟[{nℊ}⋅{𝑝𝐴ℋ}]×Σ{𝑝𝐴ℋ} + ({nℊ}⋅{𝑝𝐴ℋ})×𝒟[Σ{𝑝𝐴ℋ}]
    ({𝒟[nℊ]}⋅{𝑝𝐴ₙℋ} + {nℊ}⋅{𝒟[𝑝𝐴ℋ]})×Σ{𝑝𝐴ℋ} + ({nℊ}⋅{𝑝𝐴ℋ})×𝒟[Σ{𝑝𝐴ℋ}]
    ({n𝒟ℊ}⋅{𝑝𝐴ℋ} + {nℊ}⋅{𝑝𝐴𝒟ℋ})×Σ{𝑝𝐴ℋ} + ({nℊ}⋅{𝑝𝐴ℋ})×Σ{𝑝𝐴𝒟ℋ}
    # 𝒟ℋ = 2nℋ↓, 𝒟ℊ = -2ξℊ
    ({-2ξnℊ}⋅{𝑝𝐴ℋ} + {nℊ}⋅{𝑝𝐴(2nℋ↓)})×Σ{𝑝𝐴ℋ} + ({nℊ}⋅{𝑝𝐴ℋ})×Σ{𝑝𝐴(2nℋ↓)}
    ({-2nℊ}⋅{𝑝𝐴ξℋ} + {nℊ}⋅{𝑝𝐴(2nℋ↓)})×Σ{𝑝𝐴ℋ} + ({nℊ}⋅{𝑝𝐴ℋ})×Σ{𝑝𝐴(2nℋ↓)}
    # ξℋ = ½(ℋ↑+ℋ↓/½n↧)
    ({-2nℊ}⋅{½𝑝𝐴(ℋ↑+ℋ↓/½n↧)} + {nℊ}⋅{𝑝𝐴(2nℋ↓)})×Σ{𝑝𝐴ℋ} + ({nℊ}⋅{𝑝𝐴ℋ})×Σ{𝑝𝐴(2nℋ↓)}
    ({-2nℊ}⋅{½𝑝𝐴(ℋ↑+2nℋ↓)} + {nℊ}⋅{𝑝𝐴(2nℋ↓)})×Σ{𝑝𝐴ℋ} + ({nℊ}⋅{𝑝𝐴ℋ})×Σ{𝑝𝐴(2nℋ↓)}
    (Σ{-2nℊ½𝑝𝐴(ℋ↑+2nℋ↓)} + Σ{nℊ𝑝𝐴(2nℋ↓)})×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{𝑝𝐴(2nℋ↓)}
    (Σ{-nℊ𝑝𝐴(ℋ↑+2nℋ↓)} + Σ{nℊ𝑝𝐴(2nℋ↓)})×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{𝑝𝐴(2nℋ↓)}
    Σ{-nℊ𝑝𝐴(ℋ↑+2nℋ↓) + nℊ𝑝𝐴(2nℋ↓)}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{𝑝𝐴(2nℋ↓)}
    Σ{-nℊ𝑝𝐴ℋ↑}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{𝑝𝐴(2nℋ↓)}
    # 𝐴 = √2n↥𝐴↑ = √½n↧𝐴↓
    # 𝐴 = √[2(n+1)]𝐴↑ = 𝐴↓/√2n
    Σ{-nℊ𝑝√[2(n+1)]𝐴↑ℋ↑}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{𝑝𝐴↓/√2n(2nℋ↓)}
    Σ{-nℊ𝑝√[2(n+1)]𝐴↑ℋ↑}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{√2n𝑝𝐴↓ℋ↓}
    Σ{-nℊ√[2(n+1)]𝑝𝐴↑ℋ↑}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{√2n𝑝𝐴↓ℋ↓}
    # 𝑝 = √m↑𝑝↑/√ñ = √[ñm↓]𝑝↓  
    Σ{-nℊ√[2(n+1)]√n↑𝑝↑/√ñ𝐴↑ℋ↑}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{√2n√[ñn↓]𝑝↓𝐴↓ℋ↓}
    Σ{-n²/√½ñ ℊ𝑝𝐴ℋ}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{√2ñ𝑝↓𝐴↓ℋ↓}
    Σ{-n²/√½ñ ℊ𝑝𝐴ℋ}×Σ{𝑝𝐴ℋ} + Σ{nℊ𝑝𝐴ℋ}×Σ{√2ñ𝑝𝐴ℋ}
    Σ{-n²/√½ñ Ψₙ}×Σ{Ψₙ} + Σ{nΨₙ}×Σ{√2ñΨₙ}
    Σ{-n²/√½ñ Ψₙ*Ψₙ} + Σ{n√2ñ Ψₙ*Ψₙ}
    -√[2/ñ]Σ{n² Ψₙ*Ψₙ} + √2ñΣ{n Ψₙ*Ψₙ}
    -ñ²√[2/ñ] + ñ√2ñ   # Are you sure? It's what you'd like!
    -ñ√[2ñ] + ñ√2ñ
    -ñ√[2ñ] + ñ√2ñ
    0   # OMG, why was this so hard!

    # TODO: HERE is next...
    𝒟ₓℒ = 𝒟ₓ⧼x²⧽
