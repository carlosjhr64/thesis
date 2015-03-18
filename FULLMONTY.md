[CONTENTS](CONTENTS.md)

# The Full Monty

> This section was not in the original thesis.
> I got a bit carried away on this "Full Monty".
> So I moved most of it to a "[Scratch Work](SCRATCH.md)" section.

<!-- HIGHLIGHTS START -->
##<a name="1Pu"></a> Optimization problem
The [Optimization problem](http://en.wikipedia.org/wiki/Optimization_problem)
to be solved:

    :Minimize:   ΔxΔp
    :Subject_to: ⧼Ψₒ|𝐇|Ψₒ⧽ = Eₒ

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
due to the commutator relationship between 𝐱 and 𝐩, [&#91;𝐱,𝐩&#93;](SCRATCH.md#bST).

> TODO: section on quantum number n.

Noting that [Eₙ](SCRATCH.md#2Xh) goes as the quantum number n, and
using the definitions of Δx and Δp, I then have:

    :Minimize:   √ (⧼x²⧽-⧼x⧽²)(⧼p²⧽-⧼p⧽²)
    :Subject_to: ⧼n⧽ = ñ

where [ñ](SCRATCH.md#Ojo) is the average quantum number.

##<a name="Nde"></a> ⧼𝐱⧽

    ⧼𝐱⧽
    ⧼x⧽                 # 𝐱 is just x.
    ⧼Ψₒ|ₙ⧽⧼ₙ|x|ₘ⧽⧼ₘ|Ψₒ⧽ # Expand out expression.
    ⨋ₓ(𝑝ₙΨₙ)*x(𝑝ₘΨₘ)    # Switched from ⧼⧽ to ⨋ₓ notation.
    ⨋ₓ𝒫ₙₘΨₙ*xΨₘ         # 𝒫ₙₘ = 𝑝ₙ*𝑝ₘ
    ⨋ₓ𝒫 Ψ*xΨₘ           # Implicit n, explicit m.
    ⨋ₓ𝒫 Ψ*√𝒽ξΨₘ         # Change of variable, x to ξ.
    √𝒽⨋ 𝒫 Ψ*ξΨₘ         # Take √𝒽 outside.

The [𝒽](SCRATCH.md#hIf) is there because x=√𝒽ξ, a shorthand to ħ/(μω).
It's just a constant.

    √𝒽⨋ 𝒫 Ψ*ξΨₘ                  # Continue from above.
    √𝒽⨋ 𝒫 (ξΨ)*Ψₘ                # Rearrange, want ξΨ.
    √𝒽⨋ 𝒫 √½(√n↥Ψ↑+√ŉ↧Ψ↓)*Ψₘ     # Subtitute for ξΨ.
    √½𝒽⨋ 𝒫 (√n↥Ψ↑+√ŉ↧Ψ↓)*Ψₘ      # Factor out the √½.
    √½𝒽⨋ 𝒫 (√n↥Ψ↑*Ψₘ+√ŉ↧Ψ↓*Ψₘ)   # Distribute Ψₘ.
    √½𝒽⅀ 𝒫 (√n↥𝛿↑+√ŉ↧𝛿↓)
    √½𝒽⅀ 𝑝*𝑝ₘ(√n↥𝛿↑+√ŉ↧𝛿↓)       # 𝑝*𝑝ₘ = 𝒫 .
    √½𝒽⅀ 𝑝*(√n↥𝑝ₘ𝛿↑+√ŉ↧𝑝ₘ𝛿↓)     # Distribute 𝑝ₘ.
    √½𝒽⅀ 𝑝*(√n↥𝑝ₘ↑𝛿+√ŉ↧𝑝ₘ↓𝛿)
    √½𝒽∑ 𝑝*(√n↥𝑝↑+√ŉ↧𝑝↓)
    √½𝒽∑ 𝑝*(√[n+1]𝑝↑+√n𝑝↓)       # Evaluate "factorals".
    √½𝒽∑ 𝑝ₙ*(√[n+1]𝑝ₙ₊₁+√n𝑝ₙ₋₁)  # Explicit n.

> TODO: Need to explain how 𝛿↑ and 𝛿↓ work.

##<a name="2Nz"></a> Resources
On top of the references given in the appendix,
I'd like to add (or reiterate) the following resources:

* Liboff's book, [Introductory Quantum Mechanics](https://books.google.com/books?id=FbIPAQAAMAAJ&dq=editions:0s8yO_VH82AC&hl=en&sa=X&ei=v5L9VNCcBpLkoATB1IGAAQ&ved=0CDsQ6AEwBg).
* njwildberger's [MathFoundations](https://www.youtube.com/playlist?list=PL5A714C94D40392AB)
* Stanford's Susskind's [Advanced Quantum Mechanics](https://www.youtube.com/playlist?list=PLpGHT1n4-mAsmMxmSX0LCaXIXT2PmU85m)
* jodiecongirl's [A Lagrange Multiplier Example](https://youtu.be/H4HN4ZrVm0w)
* mathdude2012's [Uncertainty Principle with Time and Energy](https://www.youtube.com/watch?v=Eb3V8GrR7jk)
* professofleonard57's [Series, Geometric Series, Harmonic Series, and Divergence Test](http://youtu.be/DGcWMdW-72M)
* MindYourDecisions' [What is the factorial of 1/2? The surprising answer: (1/2)!=(√π)/2](http://youtu.be/QhDDpSju3uY)

So the way it works is that any mistakes herein are all my fault.
If I say anything good, it's because of these other people:
<!-- HIGHLIGHTS END -->

[CONTENTS](CONTENTS.md)
