[CONTENTS](CONTENTS.md)

# The Full Monty
Here I write explicitly all my work, as if writting computer code.
Consider all symbols to have global scope.
Each symbol should only be defined once,
except `u` and `v` which will be used as temporary general variables.
In books you'll see `sin²(x)` to mean `sin(x)×sin(x)`.
I'll use that convention in general.
`u²[v]` will mean `u[v]×u[v]` and not `u[u[v]]`.
The initial part of this section goes over elementary material, but
it's a good warmup and demonstrates my notation.

> This section was not in the original thesis.
> Eventually I hope to have the entire work in one stream of "mathematical code".
> Please use github to contact me to let me know of any errors (of any type).

<!-- TOC START -->
## Sections:
<font size="+1">

 · [Expressions](#1) · [{u,v,w}](#2) · [Precedence rules](#3) · [ℕ](#4) · [ℤ and ℚ](#5) · [uᵥ](#6) ·

 · [Π](#7) · [uᵛ](#8) · [√u](#9) · [|u|](#10) · [Σ](#11) · [n×u](#12) ·

 · [⇊,↓,↑,⇈](#13) · [↧,↥](#14) · [Σu↑](#15) · [∑](#16) · [∑u↑](#17) · [∑u↓](#18) ·

 · [𝐿](#19) · [uₒ≡Σuₙ](#20) · [ℝ](#21) · [ℂ](#22) · [𝑖](#23) · [*](#24) ·

 · [&lt;u&gt;](#25) · [n!](#26) · [(ⁿₘ)](#27) · [nₘ](#28) · [0ₘ](#29) · [1ₘ](#30) ·

 · [2ₘ](#31) · [3ₘ](#32) · [nₘ=(n+m)!/n!](#33) · [n₋ₘ=(n-m)!/n!](#34) · [n₋ₙ=1/n!](#35) · [(ⁿₘ)=m-ₘ/n-ₘ](#36) ·

 · [n↥,n₀,n↧](#37) · [nᵥn!](#38) · [Sine](#39) · [Cosine](#40) · [ℯ](#41) · [Δ²](#42) ·

 · [𝑃ₙ](#43) · [pₙ](#44) · [K,m](#45) · [ħ](#46) · [π](#47) · [ω](#48) ·

 · [f](#49) · [Eₙ](#50) · [⌽ᵗₙ](#51) · [⌽→φ](#52) · [ñ](#53) · [𝐿 Σ[n(n-1)𝑃ₙ]](#54) ·

 · [p→𝑃](#55) · [ξ](#56) · [𝐴ₙ](#57) · [ℋₙ](#58) · [Ψₙ](#59) · [ξΨₘ](#60) ·

 · [&lt;ξ₀&gt;](#61) · [⌽𝐴ℋ↓/½n↓=⌽↥/√½n↓⌽↓Ψ↓](#62) · [⌽𝐴ℋ↑=⌽↧√2n↑⌽↑Ψ↑](#63) · [p↑p=√[ñ/n↑]𝑃](#64) · [p↓p=𝑃/√[n↓ñ]](#65) · [&lt;ξₜ&gt;](#66) ·

 · [&lt;ξ²&gt;](#67) · [Δ²ξ](#68) · [Resources](#69) ·


</font>
<!-- TOC END -->

##<a name="1"></a> Expressions
This file is written in [Markdown](http://en.wikipedia.org/wiki/Markdown) format.
Proper mathematical
[Expressions](http://en.wikipedia.org/wiki/Expression_%28mathematics%29)
will start with four spaces and end with either a newline or a pound sign, `#`.
Everything else is commentary.

> TODO:
> Rules for expression than end with `=` and `→` which then
> continue on the next line are emerging, but
> I haven't yet decided exactly what they are.

> TODO:
> Convention on alphabet/letter use?

##<a name="2"></a> {u,v,w}
Arbitrary symbols:

     {u,v}           # I conjure up u and v of any type.
     w≡v → w=v       # If I define w as v, then w is v, capiche?
     u≡u             # So I tell you things are themselves.
     u=u             # Then you accept things are themselves.
     w=v,v=u → w=u   # Transitive Property of Equality.

##<a name="3"></a> Precedence rules
The following precedence rules are in order:

    u⇤u ≡ (u⇤)u       # Left binding operator.
    u⇥v ≡ u(⇥v)       # Right binding operator.
    u v w ≡ (u(vw))   # "Σ uv" means "Σ[uv]", not "Σ[u]v".
    uvw ≡ ((uv)w)     # Default way to read expressions.

    (⇤){(ᵛ),(ᵥ)}   # Superscripts and subscripts are left binding operators.
    (⇤){(!)}       # Factorial is a left binding operator.

    wᵘᵥ ≡ (wᵥ)ᵘ   # This weirdness is due to the sin²(x)=sin(x)*sin(x) convention.

    (⇥){(2),(½)}   # 2 and ½ bind right.  I don't think I use any other literal values.

    # Examples:
    u2vw = (u(2v))w
    u½vw = (u(½v))w
    u ½ v w = u(½(vw))
    u½ v w = (u½)(vw)   # But this would be weird, I would not write it this way.
    u!vw = ((u!)v))w
    2³₄ = (2₄)³         # This is not 8₄.  I would just write (2₄)³ to avoid confusion.

Some of these rules help compact the notation as it most commonly appears.
For example, `√2πx` is `√[2π]x`, but `√nπx` is `√[n]πx`.

##<a name="4"></a> ℕ
Natural (Counting) numbers:

    ℕ ≡ {0,1,2,3,⋯}   # The set of Natural numbers.  Or the ordered type /^\d+$/.
    ℕ{N,n,m}          # N, M, n, and m are Natural numbers.
    M≡N-1             # This just simplifies notation later on.

##<a name="5"></a> ℤ and ℚ
See njwildberger's [MathFoundations](https://www.youtube.com/user/njwildberger).
Integers and Rationals:

    ℤ ≡ ℕ - ℕ          # u-v, like 1-2 or just "-1".
    ℚ ≡ ℤ / ℕ{n:n≠0}   # u/v, like ½ or just "0.5".
    ℤ{l,k}             # l and k are Integers.

##<a name="6"></a> uᵥ
Subcripts labels a specific form of a more general expression:

    uᵥ[⋯]≡u[v,⋯]
    uₙₘ≡u[n,m,⋯]

Sequences can be thought of the set `{uₙ}`, but in this "paper",
`uₙ` is always a well defined expression.

##<a name="7"></a> Π
Products of sequences,
[`Π`](http://en.wikipedia.org/wiki/Multiplication#Capital_Pi_notation):

    # 1.upto(m).inject(1){|v,n|v×u[n]}
    Π[1,0] ≡ 1
    Π[1,m]{n|uₙ} ≡ u₁×u₂×⋯×uₙ₋₁×uₙ×uₙ₊₁×⋯×uₘ₋₁×uₘ
    Π[1,2]{u} = u×u
    Π[1,3]{n|n} = 1×2×3

##<a name="8"></a> uᵛ
Superscripts normally are ℕ denoting repetition:

    uⁿ ≡ Π[1,n]{u}
    u⁰=1
    u¹=u
    u²=uu    # Square
    u³=uuu   # Cube

    uᵐₙ ≡ (uₙ)ᵐ         # I don't use uₙ², but it's probably u[n²].
    uⁿ[v] ≡ (u[v])ⁿ
    u²[v] = u[v]×u[v]   # For example: "sin²(x) = sin(x)sin(x)"

Superscripts also denotes power or raising operations:

    uᵛ ≡ u^v   # or "u**v" in Ruby.

##<a name="9"></a> √u
Squareroot:

    √[u²]≡u
    √u²=u   # By precedence rules and definition.
    √[uu]=u

##<a name="10"></a> |u|
Absolute value:

    |u|≡(u>0)?u:-u  ←  ℚ{u}

##<a name="11"></a> Σ
Summation over ℕ indeces:

    Σuₙ ≡ u₀ + u₁ + u₂ + ⋯   # Non-halting series.
    ΣΣuₙₘ ≡ (u₀₀ + u₀₁ + u₀₂ + ⋯) + (u₁₀ + u₁₁ + u₀₂ + ⋯) + (u₂₀ + u₂₁ + u₂₂ + ⋯) + ⋯

    Σₙuₙ ≡ Σ[0,M]{n|u[n]}   # NOTE!  Series indeces start with zero.
    ΣₙΣₘuₙₘ ≡ Σ[0,M]{n| Σ[0,M]{m| u[n,m]}}

    N = Σₙ 1

##<a name="12"></a> n×u
Just regular multiplication:

    n×u ≡ Σ[0,n]{u}
    nu ≡ n×u
    n/m × u/v = (n×u)/(m×v)

##<a name="13"></a> ⇊,↓,↑,⇈
Arrow Operators on subscripts:

    uₗ↑ ≡ uₗ₊₁
    uₗ↓ ≡ uₗ₋₁

    uₗ⇈ ≡ uₗ↑↑
    uₗ⇈ = uₗ₊₂

    uₗ⇊ ≡ uₗ↓↓
    uₗ⇊ = uₗ₋₂

    uₗ↑ⁿ ≡ uₗ₊ₙ
    uₗ↓ⁿ ≡ uₗ₋ₙ

    Σₙu↑ ≡ Σₙuₙ₊₁   # Where context allows, subscript not needed.

##<a name="14"></a> ↧,↥

    u↥ ≡ u₀↑   # Step up from "ground", just to make notation "pretty" later on.
    u↥ = u₁

    u↧ ≡ u₀↓   # Step down from "ground".
    u↧ = u₋₁

    u↥ⁿ ≡ uₙ
    u↧ⁿ ≡ u₋ₙ

##<a name="15"></a> Σu↑

    Σₙuₙ = +u₀ + Σₙuₙ₊₁ - u[N]
    Σₙuₙ = +u₀ + Σₙu↑ - u[N]

    Σuₙ = u₀ + Σu↑

##<a name="16"></a> ∑
This is interesting.
Looks like I'm going to have to argue `∑` over `ℤ` vs. `Σ` over `ℕ`.
Summation over ℤ indeces:

    ∑uₗ ≡ ⋯ + u₋₂ + u₋₁ + u₀ + u₁ + u₂ + ⋯
    ∑ₗuₗ ≡ Σ[-M,M]{l|uₗ}   # Halting version of ∑

    ∑ₗ1 = 2M+1 = 2N-1

    ∑∑ uₗvₖ = ∑uₗ × ∑vₗ

The argument later will sound like a state can be created
from "nothing" and destroyed to "nothing"...  as long as "What!?"

##<a name="17"></a> ∑u↑

    ∑ₗuₗ = +u[-M] + ∑ₗuₗ₊₁ - u[N]
    ∑ₗuₗ = +u[-M] + ∑ₗu↑ - u[N]

    ∑uₗ = ∑u↑   # It's the same!

##<a name="18"></a> ∑u↓

    ∑ₗuₗ = -u[-N] + ∑ₗuₗ₋₁ + u[M]
    ∑ₗuₗ = -u[-N] + ∑ₗu↓ + u[M]

    ∑uₗ = ∑u↓   # Same!

##<a name="19"></a> 𝐿
The limit fuction, `𝐿`.
N is very, very, big!
I want try to keep things simple and
avoid a full treatment of limits.
Let's try a simple limit function:

    𝐿 Σuₙ ≡ 𝐿 Σₙuₙ               # 𝐿 truncates the series to down to N elements.
    𝐿[u+v] ≡ 𝐿[u] + 𝐿[v]
    𝐿[u] ≡ (|u| ≥ 1/N²)? u : 0   # 𝐿 ignores very small numbers.

    𝐿 Σₙ[1/N] = Σₙ 𝐿[1/N]
      = Σₙ[1/N]
      = 1   # Notice that this would have been 0 had I set the threshold to ≥ 1/N.

    𝐿 Σₙ[1/N²] = Σₙ 𝐿[1/N²]
      = Σₙ 0
      = 0   # Is this acceptable?

    Σₙ[1/N²] = 0.5 ← N=2        # n=2; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ[1/N²] = 0.25 ← N=4       # n=4; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ[1/N²] = 0.125 ← N=8      # n=8; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ[1/N²] = 0.0625 ← N=16    # n=16; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ[1/N²] = 0.03125 ← N=32   # n=32; n.times.inject(0){|s,i|s+1.0/(n*n)}

As N doubles, the sum Σₙ[1/N²] halves.
So Σₙ[1/N²] does approach zero as N goes on to infinity.
For the following examples, I use fatorial N! and exponential function ℯ[N]:

    𝐿[u+1/N²] = u
    𝐿[u+ℯ[N]/N!] = u    # Try N≥10.
    𝐿[u+(v^N)/N!] = u   # N depends on v, but for some N it's true.
    𝐿[u+ℯ[-N]] = u      # Obviously, I hope.

    |u| ≤ 1/N, |v| ≤ 1/N  ⇒  |uv| ≤ 1/N², 𝐿[uv]=0

The Float::EPSILON for Ruby on my machine is about 2.22e-16.
So `𝐿` puts a limit on N on my machine of about 6.71e+7 (2.22e-16 ~ 1/(6.71e+7)^2).

##<a name="20"></a> uₒ≡Σuₙ
I'll use subcript o, `ₒ`, to refer to the object that represents an infinite sum.

    uₒ≡Σuₙ

##<a name="21"></a> ℝ
For the purpose of this "paper", ℝ just needs to include the series I'm working with.
That is ℝ augments ℚ with Σuₙ as follows:

    ℚ{uₙ: |uₙ|≤1/n² ← n≥N}, v=Σuₙ ↔ ℝ{v}, ℚ{𝐿[Σₙuₙ]}

So I just need `ℝ` to work with `𝐿[Σuₙ]`.
ℝ has well defined `+` and `×`:

    uₒ=Σuₙ,vₒ=Σvₙ → uₒ+vₒ ≡ Σ uₙ+vₙ, uₒvₒ ≡ ΣΣ uₙvₘ

ℝ can be scaled by a rational:

    ℚ{v,uₙ}, ℝ{uₒ:uₒ=Σuₙ} → vuₒ = vΣuₙ = Σvuₙ, ℝ{vuₒ}

Quick plausibility check:

    u=[1,2,3],v=[4,5,6] →
      uₒ = Σuₙ = 1 + 2 + 3 = 6
      vₒ = Σvₙ = 4 + 5 + 6 = 15
      # Addition
      uₒ+vₒ = Σ uₙ+vₙ = (1+4) + (2+5) + (3+6) = 5 + 7 + 9 = 21
      Σuₙ + Σvₙ = 6 + 15 = 21
      uₒ+vₒ = Σuₙ+Σvₙ = Σ uₙ+vₙ = 21   # All self consistent
      # Multiplication
      uₒvₒ = ΣΣ uₙvₘ = ((1×4)+(1×5)+(1×6)) + ((2×4)+(2×5)+(2×6)) + ((3×4)+(3×5)+(3×6))
        = (4+5+6) + (8+10+12) + (12+15+18)
        = 15 + 30 + 45
        = 90
      uₒvₒ = Σuₙ Σvₙ = 6×15 = 90
      uₒvₒ = Σuₙ Σvₙ = ΣΣ uₙvₘ = 90   # Again, consistent.
      # Division we don't have in the same form.
      uₒ/vₒ = Σuₙ/Σvₙ

    Σuₙ Σvₘ = ΣΣ uₙvₘ
    # The rigorous proof:
      Σuₙ Σvₘ
      (Σuₙ)×(Σvₘ)   # Just explicitly showing what I mean.
      Σ[uₙ×(Σvₘ)]   # Treat the v series like a number and take it into the u series.
      Σ[Σuₙvₘ)]     # uₙ is just a constant rational and can go into the v series.
      ΣΣ[uₙvₘ]      # Well... maybe it was obvious to begin with.

I'll be using ΣΣ[uₙvₘ]=Σ[uₙ]Σ[vₙ] later.

##<a name="22"></a> ℂ
Complex numbers:

    ℂ ≡ (ℝ,ℝ)
    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)+(vᵣ,vᵢ)≡(uᵣ+vᵣ,uᵢ+vᵢ)
      (uᵣ,uᵢ)(vᵣ,vᵢ)≡(uᵣvᵣ-uᵢvᵢ,uᵣvᵢ+uᵢvᵣ)
      (uᵣ,uᵢ)(uᵣ,uᵢ)=(uᵣ²-uᵢ²,2uᵣuᵢ)
      uᵣ≡(uᵣ,0)
    ℂ{α,β}

##<a name="23"></a> 𝑖
The Imaginary number 𝑖:

    𝑖 ≡ (0,1)
    𝑖² = (-1,0)
    # Proof
      (0,1)(0,1)
      (0²-1²,0×1+1×0)
      (-1,0)
    (u,v) = u+𝑖v
    𝑖² = -1

##<a name="24"></a> *
Complex conjugation:

    (u,v)* ≡ (u,-v)
    (u+𝑖v)* = u-𝑖v
    ℯ[𝑖]* = (C+𝑖S)* = C-𝑖S = ℯ[-𝑖]   # what it does to e

    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)*(vᵣ,vᵢ)=(uᵣvᵣ+uᵢvᵢ,uᵣvᵢ-uᵢvᵣ)
      (uᵣ,uᵢ)*(uᵣ,uᵢ)=(u²ᵣ+v²ᵢ,0)
      (uᵣ,0)*(vᵣ,0)=(uᵣvᵢ,0)
      uᵣ*vᵣ=uᵣvᵣ   # Notice how it does end up looking like multiplication in ℝ.

      # Just to review
      (uᵣ,uᵢ)×(vᵣ,vᵢ) = (uᵣvᵣ-uᵢvᵢ, uᵣvᵢ+uᵢvᵣ)
      (uᵣ,uᵢ)×(uᵣ,uᵢ) = (u²ᵣ-u²ᵢ, 2uᵣuᵢ)
      (uᵣ,uᵢ)*(vᵣ,vᵢ) = (uᵣvᵣ+uᵢvᵢ, uᵣvᵢ-uᵢvᵣ)
      (uᵣ,uᵢ)*(uᵣ,uᵢ) = (u²ᵣ+u²ᵢ, 0)

Maybe `*` should really be thought as a binary operator,
a special type of multiplication.

##<a name="25"></a> &lt;u&gt;
Dirac notation:

    <αu|βv> ≡ ∫{w| (αu[w])*(βv[w])}

For the case I'm working in,
u and v are a discrete set of orthogonal functions:

    uₗ*uₖ = (l=k)? uₗ² : 0

    <αu|βv> = ∑∑ (αuₗ)*(βvₖ)
    <αu|βv> = α*<u|βv> = β<αu|v>
    <αu|βv>* = <βv|αu>
    <αu| + <βv| = <αu+βv|

    <αu|βu> = (α*β)∑ uₗ*uₗ   # Orthogonal, crossterms are all 0.

    <u> ≡ <u|u>

    <αu> = α*α<u>
    # Proof
      <αu>
      <αu|αu>
      α*<u|αu>
      α*α<u|u>
      α*α<u>

    |ₖ> ≡ |uₖ>   # where u is know from context

    <u|ₖ> = uₖ*uₖ
    # Proof
      <u|ₖ>
      <u|uₖ>
      ∑ uₗ*uₖ
      uₖ*uₖ   # u are orthogonal, only the k-th term contributes.

    <uₗ> = uₗ*uₗ
    <u|ₗ> = <uₗ>
    <α> = α*α
    # TODO: What we mean by average value,  <u> ≡ Σₙuₙ/N ?

##<a name="26"></a> n!
Factorial:

    n! ≡ Π[1,n]{u|u}   # 1×2×3×...×n

    u[n]=1/n! → u[n-1]=nu[n]   # Recursion
    # Proof:
      nu[n]                    # Given
      n/n!                     # Substitution
      n/((n-1)!n)
      1/(n-1)!
      u[n-1]

    1/(-1)! = 0
    # Proof 1:
      n=0, 1/(n-1)!=n/n!
      1/(0-1)! = 0/0!   # Substitute n.
      1/(-1)! = 0/1     # 0! is just 1
      1/(-1)! = 0
    # Proof 2, by recursion:
      u[-1]
      u[0-1]
      0u[0]
      0/0!
      0/1
      0

    1/(-2)! = 0
    # Proof by recursion:
      u[-2]
      u[-1-1]
      -1u[-1]
      -1×0
      0   # In general 1/u! = 0 ← ℤ{u<0}

##<a name="27"></a> (ⁿₘ)
[Binomial coefficient](http://en.wikipedia.org/wiki/Binomial_coefficient),
n choose m:

    (ⁿₘ) ≡ n!/(m!(n-m)!)

##<a name="28"></a> nₘ
I'd like to make the following refinement in ℕ,
[Factoral](http://www.urbandictionary.com/define.php?term=Factoral&defid=5895569) forward:

    n₀ ≡  1
    nₘ ≡ (n+m)nₘ₋₁

    n₁ = (n+1)n₀ = n+1
    n₂ = (n+2)n₁ = (n+2)(n+1)
    n₃ = (n+3)n₂ = (n+3)(n+2)(n+1)
    n₄ = (n+4)n₃ = (n+4)(n+3)(n+2)(n+1)

    m>0 → nₘ=Π[1,m]{l|n+l}

##<a name="29"></a> 0ₘ

    0ₘ = Π[1,m]{l|0+l} = Π[1,m]{l|l} = m!
    0₀ = 1   # by definition
    0₁ = (0+1)1 = 1  = 1!
    0₂ = (0+2)1 = 2  = 2!
    0₃ = (0+3)2 = 6  = 3!
    0₄ = (0+4)6 = 24 = 4!
    ⋯
    0ₘ = m!

##<a name="30"></a> 1ₘ

    1₀ = 1   # by definition
    1₁ = (1+1)1  = 2   = 2!
    1₂ = (1+2)2  = 6   = 3!
    1₃ = (1+3)6  = 24  = 4!
    1₄ = (1+4)24 = 120 = 5!
    1ₘ = (m+1)!
    ⋯
    1ₘ = (m+1)!

##<a name="31"></a> 2ₘ

    2₀ = 1   # by definition
    2₁ = (2+1)1  = 3   = 6/2   = 3!/2
    2₂ = (2+2)3  = 12  = 24/2  = 4!/2
    2₃ = (2+3)12 = 60  = 120/2 = 5!/2
    2₄ = (2+4)60 = 360 = 720/2 = 6!/2
    ⋯
    2ₘ = (2+m)!/2

##<a name="32"></a> 3ₘ

    3₀ = 1   # by definition
    3₁ = (3+1)1   = 4    = 24/6   = 4!/3!
    3₂ = (3+2)4   = 20   = 120/6  = 5!/3!
    3₃ = (3+3)20  = 120  = 720/6  = 6!/3!
    3₄ = (3+4)120 = 840  = 5040/6 = 7!/3!
    ⋯
    3ₘ = (3+m)!/3!

##<a name="33"></a> nₘ=(n+m)!/n!

    nₘ=(n+m)!/n!
    # Proof:
      nₘ
      Π[1,m]{l|n+l}                 # (n+1)*(n+2)*...*(n+m)
      Π[1+n,m+n]{l|l}               # Same thing!
      Π[1,m+n]{l|l} / Π[1,n]{l|l}   # (1*2*...*n) * (n+1)*(n+2)*...*(n+m) / (1*2*...*n)
      (m+n)! / n!

##<a name="34"></a> n₋ₘ=(n-m)!/n!

    nₘ₊₁ = (n+m+1)nₘ   # by defintion ↑
    nₘ₊₁/(n+m+1) = nₘ
    nₘ = nₘ₊₁/(n+m+1)

    n₋₁ = n₀/(n-1+1)
    n₋₁ = 1/n

    n₋₂ = n₋₁/(n-2+1)
    n₋₂ = 1/(n(n-1))

    n₋₃ = 1/(n(n-1)(n-2))
    n₋₄ = 1/(n(n-1)(n-2)(n-3))

    n₋ₘ = (n-m)!/n!  ← m≤n   # Amazing, works backwards too!

##<a name="35"></a> n₋ₙ=1/n!

    n₋ₙ = 1/(n(n-1)...(n-n+1)) = 1/(n(n-1)...(1)) = 1/n!
    n₋ₙ₋₁ = 1/(n!(0))
    n₋ₙ₋₂ = 1/(n!(0)(-1))
    n₋ₙ₋₃ = 1/(n!(0)(-1)(-2))
    n₋ₘ=(-1ᵐ⁻ⁿ⁺¹/(n!0(m-n+1)!) ← m>n   # Anyways, a division by zero.

##<a name="36"></a> (ⁿₘ)=m-ₘ/n-ₘ

    (ⁿₘ) = m-ₘ/n-ₘ
    # Proof
      (ⁿₘ)
      n!/(m!(n-m)!)
      n!/(m!n!n-ₘ)
      1/(m!n-ₘ)
      m-ₘ/n-ₘ

    # Some random exercises on nₘ
    0ₙn₋ₙ = (n!)(1/n!) = 1
    n₁1ₙ = (n+1) (1+1)⋯(1+n) = (n+1)² (1+1)⋯(n) = (n₁)²1ₙ₋₁
    2₃1₃ = (2+1)(2+2)(2+3) (1+1)(1+2)(1+3) =  3*4*5 * 2*3*4 = 2*(3*4)²*5 = 1₁(2₂)²4₁
    5₂8₈ = 6*7 * 9*⋯*16
    1₆5₆ = 2*⋯*7 * 6*⋯*11 = 2*⋯*5 * (6*7)² * 8*⋯*11 = 1₄(5₂)²7₄
    15₄5₁₆ = 16*⋯*19 * 6*⋯21 = 6*⋯*15 * (16*⋯*19)² * 20*21 = 5₁₀(15₄)²19₂

##<a name="37"></a> n↥,n₀,n↧
Arrows meaningful as Factorals:

    n↥⇈ = n↥³ = (n+1)(n+2)(n+3)
    n₀⇈ = n↥² = (n+1)(n+2)
    n₀↑ = n↥  = n+1
    n₀        = 1
    n₀↓ = n↧  = 1/n
    n₀⇊ = n↧² = 1/(n(n-1))
    n↧⇊ = n↧³ = 1/(n(n-1)(n-2))

##<a name="38"></a> nᵥn!
Factoral with Factorial:

    nᵥn! = (n+v)!

    n₃n! = (n+1)(n+2)(n+3)n! = (n+3)!   # OK

    n-₃n! = n!/(n(n+1)(n+2))
    n-₃n! = (n-3)!(n-2)(n-1)n/(n(n-1)(n-2))
    n-₃n! = (n-3)!   # OK

    n↥n! = (n+1)!
    n↧n! = (n-1)!

    n↥²n! = (n+2)!
    n↧²n! = (n-2)!

    n↥ᵐn! = (n+m)!
    n↧ᵐn! = (n-m)!

##<a name="39"></a> Sine
[Sine](http://en.wikipedia.org/wiki/Sine#Series_definition)
series definition:

    :Sine[u] ≡ Σ (-1)ⁿ u^(2n+1) / (2n+1)!
    S[u] ≡ :Sine[u]

##<a name="40"></a> Cosine
[Cosine](http://en.wikipedia.org/wiki/Trigonometric_functions#Series_definitions)
series definition:

    :Cosine[u] ≡ Σ (-1)ⁿ u^(2n) / (2n)!
    C[u] ≡ :Cosine[u]

##<a name="41"></a> ℯ
[Exponential](http://en.wikipedia.org/wiki/Exponential_function#Formal_definition)
series definition:

    :Exponential[u] ≡ Σ uⁿ / n!
    ℯ[u] ≡ :Exponential[u]
    ℯᵘ ≡ ℯ^(u) ≡ ℯ[u]   # Alternate forms.

## S²+C²=1
[Trigonometric Identities](http://en.wikipedia.org/wiki/List_of_trigonometric_identities):

    S²+C²=1            # Pythagoras
    S[u+v]=SᵤCᵥ+CᵤSᵥ   # Sine's angle sum
    C[u+v]=CᵤCᵥ-SᵤSᵥ   # Cosine's angle sum
    C[2u]=1-2S²ᵤ       # Cosine double angle "cos(2u)=1-2sin²(u)"

Just a quick exercise.
Derivation: Cosine's Angle Sum to Cosine Double Angle:

    :Cosine[2u]
    C[2u] = C[2u]
    C[2u] = C[u+u]
    C[2u] = C[u]C[u]-S[u]S[u]
    C[2u] = CᵤCᵤ-SᵤSᵤ         # Shorten form
    C[2u] = CC-SS             # From context, C=:Cosine[u] and S=:Sine[u]
    C[2u] = C²-S²
    C[2u]-1 = C²-S²-1
    C[2u]-1 = (C²-1)-S²
    C[2u]-1 = (-S²=C²-1)-S²   # A bit of "rubyism" here.  Just invoking Pythagoras.
    C[2u]-1 = -S²-S²
    C[2u]-1 = -2S²
    C[2u] = 1-2S²
    # I should expand out the context once the shorthand has fulfilled its purpose.
    C[2u] = 1-2S²[u]
    :Cosine[2u] = 1 - 2:Sine²[u]

## ℯⁱᵘ=Cᵤ+𝑖Sᵤ
Known properties of e:

    ℯ[u]ℯ[v] = ℯ[u+v]
    ℯ[𝑖u] = C[u]+𝑖S[u]
    ℯ[-𝑖u] = C[u]-𝑖S[u]
    ℯ[0] = 1

##<a name="42"></a> Δ²
Measure of uncertainty defined (4.1a):

    Δ²[u] ≡ <(u - <u>)²>
    Δ²u ≡ <(u - <u>)²>   # Allow the shorter form if unambiguous.

    Δ[u] ≡ √[Δ²u]   # I only defined Δ² and a not in terms of Δ, so...
    Δu ≡ √[Δ²u]     # Again, allow the shorter form.

    # Deriving 4.1b:
    Δ²u = <u² - 2u<u> + <u>²>
    Δ²u = <u²> - 2<u><u> + <u>²
    Δ²u = <u²> - 2<u>² + <u>²
    Δ²u = <u²> - <u>²

Measure of uncertainty (4.1b):

    Δ²u = <u²> - <u>²

##<a name="43"></a> 𝑃ₙ
`𝑃` is the [Poisson distribution](http://en.wikipedia.org/wiki/Poisson_distribution):

    𝑃ₙ ≡ uⁿℯ[-u]/n!
    Σ 𝑃ₙ = 1
    0 ≤ 𝑃ₙ ≤ 1
    <u> = Σ 𝑃ₙuₙ

##<a name="44"></a> pₙ

    pₙ ≡ √[uⁿℯ[-u]/n!]
    pₙ*pₙ = 𝑃ₙ
    # Proof
      pₙ*pₙ
      √[uⁿℯ[-u]/n!]*√[uⁿℯ[-u]/n!]
      √[uⁿℯ[-u]/n!]√[uⁿℯ[-u]/n!]   # It's just all real.
      uⁿℯ[-u]/n!
      𝑃ₙ

##<a name="45"></a> K,m
I think the point here is that these values are "measured" by "experiment" in "some way".

    ℝ{m}   # Mass
    ℝ{K}   # Spring contant 

##<a name="46"></a> ħ
[Reduced Planck constant](http://en.wikipedia.org/wiki/Planck_constant):

    ℝ{ħ}

##<a name="47"></a> π
You can check that there exist several series 
of rational terms that produce [π](http://en.wikipedia.org/wiki/Pi).
[Leibniz_formula for π](http://en.wikipedia.org/wiki/Leibniz_formula_for_π):

    ℝ{π} ← π = 4 Σ (-1)ⁿ/(2n+1)
    # Proof:
      π
      4 Σ (-1)ⁿ/(2n+1)
      4 Σ 1/(2(2n)+1) - 1/(2(2n+1)+1)   # pairing the alternating series
      4 Σ 1/(4n+1) - 1/(4n+3)
      4 Σ ((4n+3)-(4n+1))/((4n+1)(4n+3))
      4 Σ 2/((4n+1)(4n+3))
      Σ 8/((4n+1)(4n+3))
        # Fits given definition of ℝ.
        |8/((4n+1)(4n+3))| ≤ |8/(16n²)| ≤ |1/(2n²)| ≤ 1/n² ← n≥N

##<a name="48"></a> ω

    ω² ≡ K/m   # Angular frequency
    ω = √[K/m]

##<a name="49"></a> f

    f ≡ ω/(2π)   # Frequency

##<a name="50"></a> Eₙ

    Eₙ = ωħ(n+½)   # 3.2: Energy eigen-value

##<a name="51"></a> ⌽ᵗₙ
7.17 TODO: why -𝑖Eₙt/ħ and not +𝑖Eₙt/ħ?
Time evolution:

    ⌽ᵗₙ ≡ ℯ[-𝑖ω(n+½)t] = ℯ[-𝑖Eₙt/ħ]   # NOTE! The ½ part makes this object a bit of a screw ball.
    φᵗₙ ≡ ℯ[-𝑖ωnt]                    # "How do we end up with this?" you may ask.

    ⌽ₙ*⌽ₘ = φₘ-ₙ   # You don't have to explicitly show time if it can be infered.
    # Proof:
      ⌽ₙ*⌽ₘ
      ⌽-ₙ⌽ₘ
      ℯ[𝑖ω(n+½)t - 𝑖ω(m+½)t]
      ℯ[-𝑖ω(m-n)t]
      φₘ-ₙ

    # Don't have to explicitly show quantum number if it can be infered.
    ⌽⁰ = 1
    ⌽¹ = ℯ[-𝑖ω(n+½)]
    ⌽ᵗ = (⌽¹)^t = ℯ[t × (-𝑖ω(n+½))] = ℯ[-𝑖ω(n+½)t]   # Just to show that the notation makes sense.

##<a name="52"></a> ⌽→φ

    ⌽ₙ*⌽ₙ₊₁ = φₙ₊₁-ₙ = φ₁
    φ↥ ≡ φ₀↑ = φ₁   # This will make notation very consistent later.
    ⌽ₙ*⌽ₙ₊₁ = φ↥

    ⌽ₙ*⌽ₙ₋₁ = φₙ₋₁-ₙ = φ₋₁   # Yeah... me worry about this one a little bit!  LOL
    φ↧ ≡ φ₀↓ = φ₋₁
    ⌽ₙ*⌽ₙ₋₁ = φ↧

    ⌽ₙ*⌽ₙ₊₂ = φₙ₊₂-ₙ = φ₂
    ⌽ₙ*⌽ₙ₋₂ = φₙ₋₂-ₙ = φ₋₂

# sₙ, cₙ
Short for Sine(nωt) and Cosine(nωt):

    sₙ ≡ S[nωt]
    cₙ ≡ C[nωt]
    c₂ₙ=1-2s²ₙ   # Cosine double angle in terms of c and s.

    φₙ = cₙ-𝑖sₙ   # φ in terms of c and s.

    φ₁ = c₁-𝑖s₁

    φ₋₁ = c₁+𝑖s₁   # Maybe that'll work.

    φ₁ + φ₋₁ = 2c₁
    φ↥ + φ↧ = 2c₁   # Remember this one!

    φ₁ - φ₋₁ = 2s₁
    φ↥ - φ↧ = 2s₁

    φ₂ = c₂-𝑖s₂
    φ₋₂ = c₂+𝑖s₂

    φ₋₂ + φ₂ = 2c₂
    φ↧↓ + φ↥↑ = 2c₂   # And remember this one!

##<a name="53"></a> ñ
Average Quantum number ñ

    <n> = <n|pₙ*npₙ|m> = Σ npₙpₙ = Σ n𝑃ₙ   # only n=m terms contribute

    ñ ≡ 𝐿 <n>
    ñ = 𝐿 Σ n𝑃ₙ = 𝐿 Σₙ n𝑃ₙ   # Remember that 𝐿 truncates the series.

    Σₙ n𝑃ₙ = 𝐿 Σₙ nuⁿℯ[-u]/n!                    # Just by definition of 𝑃ₙ.
     = Σ[0,M]{n|nuⁿℯ[-u]/n!}                     # Definition of Σₙ.
     = 0 + Σ[1,M]{n|nuⁿℯ[-u]/n!}                 # The first element in the series is just zero.
     = Σ[1,M]{n|uⁿℯ[-u]/(n-1)!}                  # Have the n factor absorbed by the factorial.
     = Σ[0,M-1]{n|u[n+1]ℯ[-u]/n!}                # Shift.
     = uΣ[0,M-1]{n|uⁿℯ[-u]/n!}                   # Take out a factor of u.
     = u(Σ[0,M]{n|uⁿℯ[-u]/n!} - (u^M)ℯ[-M]/M!)   # Add and subtract the an Nth element (which is M).
     = u(Σₙ𝑃ₙ) - u(u^M)ℯ[-M]/M!                  # Definition of Σₙ and 𝑃ₙ.
     = u(1) - u^(M+1)ℯ[-M]/M!                    # Poisson distribution sums up to one.
     = u - u^(M+1)ℯ[-M]/M!

    ñ = 𝐿[u - u^(M+1)ℯ[-M]/M!]
    ñ = 𝐿[u] - 𝐿[u^(M+1)ℯ[-M]/M!]
    ñ = u - 0
    ñ = u   # As expected.  :)

##<a name="54"></a> 𝐿 Σ[n(n-1)𝑃ₙ]

    𝐿 Σ n(n-1)𝑃ₙ
    𝐿 Σₙ n(n-1)𝑃ₙ
    𝐿 Σₙ 1/n₋₂ uⁿℯ[-u]/n!
    𝐿 Σₙ uⁿℯ[-u]/(n-2)!
    𝐿 Σₙ u² u^(n-2)ℯ[-u]/(n-2)!
    𝐿 u² Σₙ u^(n-2)ℯ[-u]/(n-2)!
    𝐿 u² Σ[0,M]{n|u^(n-2)ℯ[-u]/(n-2)!}
    𝐿 u² Σ[-2,M-2]{n|uⁿℯ[-u]/n!}
    𝐿 u² (Σ[-2,-1]{n|uⁿℯ[-u]/n!} + Σ[0,M-2]{n|uⁿℯ[-u]/n!})
    𝐿 u² (Σ[-2,-1]{n|uⁿℯ[-u]/n!} + Σ[0,M-2]{n|𝑃ₙ})
    u²(𝐿[ℯ[-u]/(u²(-2)!)] + 𝐿[ℯ[-u]/(u(-1)!)] + 𝐿[Σ[0,M-2]{n|𝑃ₙ}])
    u²(0 + 0 + 𝐿[Σ[0,M-2]{n|𝑃ₙ}])   # 1/u! = 0 if integer u < 0
    u²(𝐿[Σ[0,M]{n|𝑃ₙ} - 𝑃[M-1] - 𝑃[M]])
    u²(𝐿[Σ𝑃ₙ - 𝑃[M-1] - 𝑃[M]] - 𝑃[M+1] - ⋯)   # Re-consider the infinite series.
    u²(𝐿[1 - 𝑃[M-1] - 𝑃[M]] - 𝑃[M+1] - ⋯)     # Σ𝑃ₙ = 1
    u²(1 - 𝐿[𝑃[M-1] - 𝑃[M]] - 𝑃[M+1] - ⋯])
    # To 𝐿, for large enough M, the trailing sequence are all zeroes.
    u²(1 - Σ0)
    u²(1-0)
    u²×1
    u²

    ñ² = 𝐿 Σ[n(n-1)𝑃ₙ]   # b/c ñ=u, so u²=ñ²

Now we can describe the distribution in terms of the average quantum number:

    𝑃ₙ = ñⁿℯ[-ñ]/n!
    pₙ = √[ñⁿℯ[-ñ]/n!]

##<a name="55"></a> p→𝑃

    pₙpₙ₊₁ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁺¹ℯ[-ñ]/(n+1)!]
           = √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!] √[ñ/(n+1)] 
           = pₙ pₙ √[ñ/(n+1)] 
           = 𝑃ₙ √[ñ/(n+1)] 
           = √[ñ/(n+1)]𝑃ₙ 
    pₙpₙ₊₁ = √ñ𝑃ₙ/√n₁   # Using Factoral
    pp↑ = √ñ𝑃ₙ/√n↑      # And Arrow notation

    pₙpₙ₋₁ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁻¹ℯ[-ñ]/(n-1)!]
           = √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!] √[n/ñ] 
           = pₙ pₙ √[n/ñ] 
           = 𝑃ₙ √[n/ñ] 
           = √[n/ñ]𝑃ₙ 
    pₙpₙ₋₁ = 𝑃ₙ/√[ñn₋₁]   # Using Factoral
    pp↓ = 𝑃ₙ/√[ñn↓]       # And Arrow notation

    pₙpₙ₊₂ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁺²ℯ[-ñ]/(n+2)!]
           = √[ñ²/((n+1)(n+2))] √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!]
           = ñ/√[(n+1)(n+2)] pₙpₙ
           = ñ/√[(n+1)(n+2)] 𝑃ₙ
    pₙpₙ₊₂ = ñ𝑃ₙ/√n₂   # Using Factoral
    pₙpₙ₊₂ = ñ𝑃ₙ/√n⇈   # Using Arrow

    pₙpₙ₋₂ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁻²ℯ[-ñ]/(n-2)!]
           = √[(n-1)n/ñ²] √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!]
           = √[(n-1)n]/ñ pₙpₙ
           = √[(n-1)n]/ñ 𝑃ₙ
    pₙpₙ₋₂ = 𝑃ₙ/(ñ√n₋₂)   # Using Factoral
    pₙpₙ₋₂ = 𝑃ₙ/(ñ√n⇊)    # Using Arrow

    p = √m↑p↑/√ñ
    # Proof:
      pp↑ = √ñ𝑃/√m↑
      p↑ = √ñp/√m↑
      √m↑p↑/√ñ = p
      p = √m↑p↑/√ñ

    p = √[ñm↓]p↓  
    # Proof:
      pp↓ = 𝑃/√[ñm↓]
      p↓ = p/√[ñm↓]
      √[ñm↓]p↓ = p
      p = √[ñm↓]p↓

##<a name="56"></a> ξ
The non-dimensional displacement, ξ.

    ξ² ≡ mω/ħ x²   # A.1b
    x² = ħ/(mω) ξ²

##<a name="57"></a> 𝐴ₙ
The Normalization Constant, 𝐴ₙ:

    𝐴ₙ ≡ 1/√[2ⁿn!√π]
    𝐴ₙ/𝐴ₙ₋₁ = 1/√[2n]
    Proof:
      (1/√[2ⁿn!√π]) / (1/√[2ⁿ⁻¹(n-1)!√π])
      (1/√[2ⁿn!√π]) × (√[2ⁿ⁻¹(n-1)!√π])
      √[2ⁿ⁻¹(n-1)!√π] / √[2ⁿn!√π]
      √[2ⁿ⁻¹(n-1)!] / √[2ⁿn!]   # √π cancels
      √[2ⁿ⁻¹] / √[2ⁿn]          # n!/(n-1)! = n
      1 / √[2n]                 # 2ⁿ/2ⁿ⁻¹ = 2

    # Identities:
    𝐴ₙ   = 𝐴ₙ₋₁ / √[2n]       # Given
    𝐴ₙ₊₁ = 𝐴ₙ   / √[2(n+1)]   # Increment index n
    𝐴ₙ   = 𝐴ₙ₊₁ × √[2(n+1)]   # Solve for 𝐴ₙ
    𝐴ₙ₋₁ = 𝐴ₙ   × √[2n]       # Decrement index n

    # With Factorals
    𝐴ₙ   = 𝐴ₙ₋₁ × √[½n₋₁] = 𝐴ₙ₋₁ × √[½n↓] = 𝐴ₙ₋₁ × √[½n↓]
    𝐴ₙ₊₁ = 𝐴ₙ   / √[2n₁]  = 𝐴ₙ   / √[2n↑] = 𝐴ₙ   / √[2n↑]
    𝐴ₙ   = 𝐴ₙ₊₁ × √[2n₁]  = 𝐴ₙ₊₁ × √[2n↑] = 𝐴ₙ₊₁ × √[2n↑]
    𝐴ₙ₋₁ = 𝐴ₙ   / √[½n₋₁] = 𝐴ₙ   / √[½n↓] = 𝐴ₙ   / √[½n↓]

    # Use these:
    𝐴ₘ = √[2m↑]𝐴ₘ↑ = √[½m↓]𝐴ₘ↓

##<a name="58"></a> ℋₙ
The Hermite polynomial:

    ℋₙ[ξ] ≡ (-1)ⁿ ℯ[ξ²] Dᵧⁿ ℯ[-ξ²]   # A.3, this is "physicists' Hermite polynomials" in Wikipedia.

    Dᵧ ℋₙ[ξ] = 2nℋₙ₋₁[ξ]   # A.4a
    # Proof:
      # It's actually a well known property of ℋ.
      # In my notes I review a proof by genetating function... unreadable to me now.
      # But found this elegant proof online,
      # http://math.stackexchange.com/questions/581897/hermite-polynomials-recurrence-relation:
      D ℋₙ[ξ]                                               # Given
      D[(-1)ⁿ ℯ[ξ²] (D)ⁿ ℯ[-ξ²]]                            # Substitution, definition of ℋ
      (-1)ⁿ D[ℯ[ξ²] (D)ⁿ ℯ[-ξ²]]                            # Take out the constant
      (-1)ⁿ (D[ℯ[ξ²]] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²] D[(D)ⁿ ℯ[-ξ²]])   # Product rule
      (-1)ⁿ (D[ℯ[ξ²]] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²] (D)ⁿ D[ℯ[-ξ²]])   # Well... obviously we're going to do that!
      (-1)ⁿ (2ξℯ[ξ²] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²] (D)ⁿ -2ξℯ[-ξ²])    # Executing D
      # I don't remember ever coming across the General Leibniz rule
      # http://en.wikipedia.org/wiki/General_Leibniz_rule
      # Let (ⁿₘ) mean n choose m.
      (-1)ⁿ (2ξℯ[ξ²] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²] Σ[0,n]{m| (ⁿₘ) (D)ᵐ[-2ξ] (D)ⁿ-ᵐℯ[-ξ²]})   # General Leibniz rule
      # D²[-2ξ]=0, (D)ⁿ[-2ξ]=0 if n>1.
      (-1)ⁿ (2ξℯ[ξ²] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²] Σ[0,1]{m| (ⁿₘ) (D)ᵐ[-2ξ] (D)ⁿ-ᵐℯ[-ξ²]})
      (-1)ⁿ (2ξℯ[ξ²] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²]((ⁿ₀) D⁰[-2ξ] (D)ⁿ-⁰ℯ[-ξ²] + (ⁿ₁) D¹[-2ξ] (D)ⁿ⁻¹ℯ[-ξ²])
      (-1)ⁿ (2ξℯ[ξ²] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²](   1 D⁰[-2ξ] (D)ⁿ  ℯ[-ξ²] +    n D¹[-2ξ] (D)ⁿ⁻¹ℯ[-ξ²])
      (-1)ⁿ (2ξℯ[ξ²] (D)ⁿ ℯ[-ξ²] + ℯ[ξ²](         -2ξ  (D)ⁿ  ℯ[-ξ²] +     n   (-2)  (D)ⁿ⁻¹ℯ[-ξ²])
      (-1)ⁿ (2ξℯ[ξ²](D)ⁿℯ[-ξ²] - 2ξℯ[ξ²](D)ⁿℯ[-ξ²] - 2nℯ[ξ²](D)ⁿ⁻¹ℯ[-ξ²])
      (-1)ⁿ (0 - 2nℯ[ξ²](D)ⁿ⁻¹ℯ[-ξ²])
      (-1)ⁿ (-2) nℯ[ξ²](D)ⁿ⁻¹ℯ[-ξ²]
      (-1)ⁿ⁻¹ 2 nℯ[ξ²](D)ⁿ⁻¹ℯ[-ξ²]
      2n (-1)ⁿ⁻¹ ℯ[ξ²] (D)ⁿ⁻¹ℯ[-ξ²]
      2n ℋₙ₋₁[ξ]

    ℋₙ₊₁[ξ] = 2ξℋₙ[ξ] - 2nℋₙ₋₁[ξ]   # A.4b
    # Also a well known property of ℋ, but here's a proof:
      ℋₙ₊₁[ξ]
      (-1)ⁿ⁺¹ ℯ[ξ²] (D)ⁿ⁺¹ ℯ[-ξ²]
      (-1)ⁿ(-1) ℯ[ξ²] (D)ⁿ[D ℯ[-ξ²]]
      (-1)ⁿ(-1) ℯ[ξ²] (D)ⁿ[(-2ξ) ℯ[-ξ²]]
      (-1)ⁿ     ℯ[ξ²] (D)ⁿ[  2ξ  ℯ[-ξ²]]
      (-1)ⁿ ℯ[ξ²] Σₘ (ⁿₘ) (D)ᵐ[2ξ] (D)ⁿ-ᵐ[ℯ[-ξ²]]                                  # General Leibniz rule
      (-1)ⁿ ℯ[ξ²]((ⁿ₀) D⁰[2ξ] (D)ⁿ-⁰[ℯ[-ξ²]] + (ⁿ₁) D¹[2ξ] (D)ⁿ⁻¹[ℯ[-ξ²]] + 0 ⋯)   # Dejavu
      (-1)ⁿ ℯ[ξ²](   1   (2ξ) (D)ⁿ  [ℯ[-ξ²]] +    n   (2)  (D)ⁿ⁻¹[ℯ[-ξ²]])
      (-1)ⁿ ℯ[ξ²](2ξ(D)ⁿ[ℯ[-ξ²]] + 2n(D)ⁿ⁻¹[ℯ[-ξ²]])
      (-1)ⁿ ℯ[ξ²] 2ξ(D)ⁿ[ℯ[-ξ²]] + (-1)ⁿ ℯ[ξ²] 2n(D)ⁿ⁻¹[ℯ[-ξ²]])                   # Distribute
      2ξ (-1)ⁿ ℯ[ξ²] (D)ⁿ[ℯ[-ξ²]] + 2n (-1)ⁿ ℯ[ξ²] (D)ⁿ⁻¹[ℯ[-ξ²]])
      2ξ (-1)ⁿ ℯ[ξ²] (D)ⁿ[ℯ[-ξ²]] + 2n (-1)(-1)ⁿ⁻¹ ℯ[ξ²] (D)ⁿ⁻¹[ℯ[-ξ²]])
      2ξ (-1)ⁿ ℯ[ξ²] (D)ⁿ[ℯ[-ξ²]] - 2n (-1)ⁿ⁻¹ ℯ[ξ²] (D)ⁿ⁻¹[ℯ[-ξ²]])
      2ξℋₙ[ξ] - 2nℋₙ₋₁[ξ]

    ξℋₙ[ξ] = ½ℋₙ₊₁[ξ] + nℋₙ₋₁[ξ]
    # Proof
      ℋₙ₊₁[ξ] = 2ξℋₙ[ξ] - 2nℋₙ₋₁[ξ]
      ℋₙ₊₁[ξ] + 2nℋₙ₋₁[ξ] = 2ξℋₙ[ξ]
      2ξℋₙ[ξ] = ℋₙ₊₁[ξ] + 2nℋₙ₋₁[ξ]
      ξℋₙ[ξ] = ½ℋₙ₊₁[ξ] + nℋₙ₋₁[ξ]


    # Can also be written as:
    Dᵧ ℋₙ[ξ] = 2nℋₙ₋₁[ξ]           = ℋₙ↓[ξ]/(½n↓)
    ξℋₙ[ξ]   = ½ℋₙ₊₁[ξ] + nℋₙ₋₁[ξ] = ½(ℋₙ↑[ξ] + ℋₙ↓[ξ]/(½n↓))

##<a name="59"></a> Ψₙ
Please accept the EigenState of the Simple Harmonic Oscillator Ψₙ as given by Liboff's book in page 189.
The EigenState Ψₙ:

    Ψₙ[x] ≡ |n>
    Ψₙ[x] = 𝐴ₙℋₙ[ξ]ℯ[-ξ²/2]

The State Function Ψ:

    Ψ[x] = Σ pₙ Ψₙ[x]   # TODO: or is it Σ 𝑃ₙ Ψₙ[x] ? Check Σ pₙ = 1 ?

The Problem To Be Solved

    Minimize:     <Ψ|n><n|ΔxΔp|m><m|Ψ>
    Subject to:   <Ψ|n><n|Eₙ|n><n|Ψ> = Eₒ

TODO: I just jumped from the above to the calculation of Δ²x !?
Will say something like ΣΣuₙvₘ = (Σuₙ)(Σvₙ)

##<a name="60"></a> ξΨₘ
Motivation: I will be calculating <Ψ|ξ|Ψ> later.

    ξΨₘ = ½𝐴ₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
    # Proof:
      ξΨₘ
      ξ𝐴ₘℋₘ[ξ]ℯ[-ξ²/2]
      𝐴ₘ ξℋₘ[ξ]ℯ[-ξ²/2]
      𝐴ₘ ½(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
      ½𝐴ₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))

##<a name="61"></a> &lt;ξ₀&gt;
Evaluation of `<ξ₀>`:

    <ξ₀> = <Ψ₀|ξ|Ψ₀>             # 7.14a
    <ξ₀> = <Ψ₀|n><n|ξ|m><m|Ψ₀>   # 7.14b

    <ξ₀> = ΣΣ (pₙΨₙ)* ξ (pₘΨₘ)
    <ξ₀> = ΣΣ Ψₙ*pₙ pₘξΨₘ                                          # rearrange, p is real.
    <ξ₀> = ΣΣ Ψₙ*pₙ pₘ ½𝐴ₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))                  # substitute for ξΨₘ
    <ξ₀> = ΣΣ Ψₙ*pₙ ½𝐴ₘ(pₘℋₘ↑[ξ] + pₘℋₘ↓[ξ]/(½m↓))                 # distribute pₘ
    <ξ₀> = ΣΣ[pₙΨₙ*pₙ ½𝐴ₘpₘℋₘ↑[ξ]] + ΣΣ[Ψₙ*pₙ ½𝐴ₘpₘℋₘ↓[ξ]/(½m↓)]   # separate
    <ξ₀> = ½ΣΣ[Ψₙ*pₙ pₘ 𝐴ₘℋₘ↑[ξ]] + ½ΣΣ[Ψₙ*pₙ pₘ 𝐴ₘℋₘ↓[ξ]/(½m↓)]   # take out ½
    # get the m's to match
    <ξ₀> = ½ΣΣ[Ψₙ*pₙ √m↑pₘ↑/√ñ √[2m↑]𝐴ₘ↑ℋₘ↑[ξ]] + ½ΣΣ[Ψₙ*pₙ √[ñm↓]pₘ↓ √[½m↓]𝐴ₘ↓ℋₘ↓[ξ]/(½m↓)]
    <ξ₀> = 1/√2ñΣΣ[Ψₙ*pₙ m↑pₘ↑𝐴ₘ↑ℋₘ↑[ξ]] + √½ñΣΣ[Ψₙ*pₙ pₘ↓𝐴ₘ↓ℋₘ↓[ξ]]
    <ξ₀> = 1/√2ñΣΣ[Ψₙ*pₙ m↑ pₘ↑Ψₘ↑] + √½ñΣΣ[Ψₙ*pₙ pₘ↓Ψₘ↓]
    <ξ₀> = 1/√2ñΣ[Ψₙ*pₙ n pₙΨₙ] + √½ñΣ[Ψₙ*pₙpₙΨₙ]           # Orthogonal states
    <ξ₀> = 1/√2ñΣΣ[n𝑃ₙ] + √½ñΣ[𝑃ₙ]                          # Ψₙ*Ψₙ=1, pₙpₙ=𝑃ₙ
    <ξ₀> = 1/√2ñ ñ + √½ñ
    <ξ₀> = √½ñ + √½ñ
    <ξ₀> = 2√½ñ
    <ξ₀> = √2ñ
    <ξ₀>² = 2ñ   # OK, need time development

##<a name="62"></a> ⌽𝐴ℋ↓/½n↓=⌽↥/√½n↓⌽↓Ψ↓

    ⌽𝐴ℋ↓/½n↓
    ⌽√[½n↓]𝐴↓ℋ↓/½n↓   # 𝐴=√[½n↓]𝐴↓
    ⌽𝐴↓ℋ↓/√[½n↓]
    ⌽↥⌽↓𝐴↓ℋ↓/√½n↓     # ⌽=⌽₁⌽↓
    ⌽↥/√½n↓ ⌽↓𝐴↓ℋ↓
    ⌽↥/√½n↓ ⌽↓Ψ↓

##<a name="63"></a> ⌽𝐴ℋ↑=⌽↧√2n↑⌽↑Ψ↑

    ⌽𝐴ℋ↑
    ⌽√2n↑𝐴↑ℋ↑   # 𝐴=√[2n↑]𝐴↑
    ⌽↧⌽↑√2n↑𝐴↑ℋ↑
    ⌽↧⌽↑√2n↑𝐴↑ℋ↑
    ⌽↧√2n↑ ⌽↑𝐴↑ℋ↑
    ⌽↧√2n↑ ⌽↑Ψ↑

##<a name="64"></a> p↑p=√[ñ/n↑]𝑃

    p↑p
    √[ñⁿ⁺¹ℯ[-ñ]/(n+1)!] p
    √[ñ/(n+1) ñⁿℯ[-ñ]/n!] p
    √[ñ/(n+1)]p p
    √[ñ/(n+1)]𝑃
    √[ñ/n₁]𝑃
    √[ñ/n↑]𝑃

##<a name="65"></a> p↓p=𝑃/√[n↓ñ]

   p↓p
    √[ñⁿ⁻¹ℯ[-ñ]/(n-1)!] p
    √[(n/ñ) ñℯ[-ñ]/n!] p
    √[n/ñ] p p
    √[1/(n₋₁ñ)]𝑃
    𝑃/√[n₋₁ñ]
    𝑃/√[n↓ñ]

##<a name="66"></a> &lt;ξₜ&gt;
Evaluation of `<ξₜ>`:

    <ξₜ> = <Ψ|ξ|Ψ>
    <ξₜ> = <Ψ|n><n|ξ|m><m|Ψ>
    <ξₜ> = ΣΣ (pₙ⌽ᵗₙΨₙ)* ξ (pₘ⌽ᵗₘΨₘ)
    # Parralles <ξ₀> up to the here...
    <ξₜ> = ½ΣΣ[(⌽ᵗₙΨₙ)*pₙ pₘ ⌽ᵗₘ𝐴ₘℋₘ↑[ξ]] + ½ΣΣ[⌽ᵗₙΨₙ*pₙ pₘ ⌽ᵗₘ𝐴ₘℋₘ↓[ξ]/(½m↓)]
    <ξₜ> = ½(Σ[(⌽Ψ)*p]Σ[p⌽𝐴ℋ↑[ξ]] + Σ[(⌽Ψ)*p]Σ[p⌽𝐴ℋ↓[ξ]/½n↓])            # ΣΣ[αₙβₘ]=Σ[αₙ]Σ[βₙ], context indeces.
    <ξₜ> = ½(Σ[(⌽↑Ψ↑)*p↑]Σ[p⌽↧√2n↑⌽↑Ψ↑] + Σ[(⌽↓Ψ↓)*p↓]Σ[p⌽↥/√½n↓⌽↓Ψ↓])   # TODO: What am I doing here???
    <ξₜ> = ½(Σ[(⌽↑Ψ↑)*p↑p⌽↧√2n↑⌽↑Ψ↑] + Σ[(⌽↓Ψ↓)*p↓p⌽↥/√½n↓⌽↓Ψ↓])         # Orthogonal states
    <ξₜ> = ½(Σ[p↑p⌽↧√2n↑] + Σ[p↓p⌽↥/√½n↓])                               # Normalized states, Ψ*Ψ=1
    <ξₜ> = ½(Σ[√[ñ/n↑]𝑃⌽↧√2n↑] + Σ[𝑃⌽↥/√[n↓ñ]/√½n↓])
    <ξₜ> = ½(Σ[√ñ𝑃⌽↧√2] + Σ[𝑃⌽↥/√½ñ/n↓])
    <ξₜ> = ½(Σ[√ñ𝑃⌽↧√2] + Σ[𝑃n⌽↥/√½ñ])
    <ξₜ> = ½(Σ[√2ñ𝑃⌽↧] + Σ[𝑃n⌽↥/√½ñ])
    <ξₜ> = ½(√2ñ⌽↧Σ[𝑃] + ⌽↥/√½ñΣ[𝑃n])
    <ξₜ> = ½(√2ñ⌽↧Σ[𝑃] + ⌽↥√2ñ)
    <ξₜ> = ½(√2ñ⌽↧ + ⌽↥√2ñ)
    <ξₜ> = ½√2ñ(⌽↧ + ⌽↥)
    <ξₜ> = ½√2ñ(2c₁)
    <ξₜ> = √2ñ c₁
    <ξₜ>² = 2ñ c₁
    <ξₜ>² = 2ñ:Cosine²[nwt]
    # This time I got Cosine... Why?  Not careful enough with φ↥ and φ↧?

##<a name="67"></a> &lt;ξ²&gt;
TODO: `<ξ²>`:

    # And who wants to work with this mess?
    <ξ²> = (ñ+½) +
      ½Σ ℯ[-𝑖ω(n+½)t]* √[uⁿℯ[-u]/n!] (
        ℯ[-𝑖ω((n-2)+½)t] √[n(n-1)] √[u^(n-2)ℯ[-u]/(n-2)! +
        ℯ[-𝑖ω((n+2)+½)t] √[(n+1)(n+2)] √[u^(n+2)ℯ[-u]/(n+2)!
      )
    <ξ²> = (ñ+½) + ½Σ ⌽ₙ*pₙ* (⌽ₙ₋₂√[n(n-1)]pₙ₋₂ +  ⌽ₙ₊₂√[(n+1)(n+2)]pₙ₊₂)   # 7.21
    # And much nicer...
    <ξ²> = (ñ+½) + ½Σ ⌽*p (⌽⇊/√n⇊ p⇊ +  ⌽⇈√n⇈ p⇈)         # pretty noted
    <ξ²> = (ñ+½) + ½Σ ⌽*⌽⇊/√n⇊ pp⇊ +  ⌽*⌽⇈√n⇈ pp⇈         # Distribute
    <ξ²> = (ñ+½) + ½Σ φ↧↓/√n⇊ pp⇊ +  φ↥↑√n⇈ pp⇈           # ⌽→φ
    <ξ²> = (ñ+½) + ½Σ φ↧↓/√n⇊ 𝑃/(ñ√n⇊) +  φ↥↑√n⇈ ñ𝑃/√n⇈   # p->𝑃
    <ξ²> = (ñ+½) + ½Σ φ↧↓/n⇊ 𝑃/ñ +  φ↥↑ ñ𝑃                # Simplify
    <ξ²> = (ñ+½) + ½Σ φ↧↓ n(n-1) 𝑃/ñ +  φ↥↑ ñ𝑃            # 1/n⇊ = n(n-1)
    <ξ²> = (ñ+½) + ½(Σ[φ↧↓ n(n-1) 𝑃/ñ] +  Σ[φ↥↑ ñ𝑃])      # Separate sums
    <ξ²> = (ñ+½) + ½(φ↧↓/ñΣ[n(n-1)𝑃] +  φ↥↑ñΣ[𝑃])         # Take out the constants
    <ξ²> = (ñ+½) + ½(φ↧↓/ñ(ñ²) +  φ↥↑ñ(1))                # Evaluate sums
    <ξ²> = (ñ+½) + ½(φ↧↓ñ + φ↥↑ñ)                         # Simplify
    <ξ²> = (ñ+½) + ½ñ(φ↧↓ + φ↥↑)
    <ξ²> = (ñ+½) + ½ñ(2c₂)                                # Remember?  φ↧↓+φ↥↑=2c₂.
    <ξ²> = (ñ+½) + ñc₂
    <ξ²> = (ñ+½) + ñ(1-2s²₁)                              # Double angle, c₂=1-2s²₁
    <ξ²> = (ñ+½) + ñ- 2ñs²₁
    <ξ²> = 2ñ + ½ - 2ñs²₁
    <ξ²> = ½ + 2ñ - 2ñs²₁
    <ξ²> = ½ + 2ñ(1 - s²₁)
    <ξ²> = ½ + 2ñc²₁                                      # Pythagoras
    <ξ²> = ½ + 2ñ:Cosine²[nwt]

##<a name="68"></a> Δ²ξ
7.5 Results:

    Δ²ξ = <ξ²> - <ξ>²
        = (½ + 2ñc²₁) - 2ñc²₁
        = ½

##<a name="69"></a> Resources
On top of the references given in the appendix, I'd like to add the following resources:

* njwildberger's [MathFoundations](https://www.youtube.com/playlist?list=PL5A714C94D40392AB)
* Stanford's Susskind's [Advanced Quantum Mechanics](https://www.youtube.com/playlist?list=PLpGHT1n4-mAsmMxmSX0LCaXIXT2PmU85m)

So the way it works is that any mistakes herein are all my fault.
If I say anything good, it's because of these other people:
