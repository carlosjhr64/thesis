[CONTENTS](CONTENTS.md)

# The Full Monty
Here I write explicitly all my work, as if writting computer code.
Consider all symbols to have global scope.
Each symbol should only be defined once, except `u` and `v` which will be used as temporary general variables.
In books you'll see `sin²(x)` to mean `sin(x)×sin(x)`.
I'll use that convention in general.
`u²[v]` will mean `u[v]×u[v]` and not `u[u[v]]`.
The initial part of this section goes over elementary material, but
it's a good warmup and demonstrates my notation.

> This section was not in the original thesis.
> Because I have UTF-8 available, I'll try to better match the expected notation.
> I've switched  notation 
> for the time development from `1ₙ` to `⌽ₙ`,
> for the non-dimensional displacement from `y` to `ξ`,
> for the Dirac notation from `<n]` to `<n|`, and
> for the variance(uncertainty) operator from `d²` to `Δ²`.
> Eventually I hope to have the entire work in one stream of "mathematical code".
> Please use github to contact me to let me know of any errors (of any type).

<!-- TOC START -->
### Sections:

[Expressions](#1) | [{u,v,w}](#2) | [Precedence rules](#3) | [ℕ](#4) | [ℤ and ℚ](#5) | [uᵥ](#6) | [Π](#7) | [uᵛ](#8)

[√u](#9) | [|u|](#10) | [Σ](#11) | [n×u](#12) | [Arrow operators](#13) | [Σu↑](#14) | [Σu↓](#15) | [∑](#16)

[∑u↑](#17) | [∑u↓](#18) | [𝐿](#19) | [ℝ](#20) | [ℂ](#21) | [i](#22) | [*](#23) | [&lt;u&gt;](#24)

[n!](#25) | [nᵥ](#26) | [nᵥn!](#27) | [(ⁿₘ)](#28) | [Sine, Cosine, and Exponential](#29) | [Δ²](#30) | [𝑃ₙ](#31) | [pₙ](#32)

[Fundamental values](#33) | [Derived values](#34) | [⌽ᵗₙ](#35) | [⌽→φ](#36) | [ñ](#37) | [𝐿 Σ[n(n-1)𝑃ₙ]](#38) | [p→𝑃](#39) | [ξ](#40)

[𝐴ₙ](#41) | [ℋₙ](#42) | [Ψₙ](#43) | [ξΨₘ](#44) | [&lt;ξ₀&gt;](#45) | [⌽𝐴ℋ↓/½n↓=⌽↥/√½n↓⌽↓Ψ↓](#46) | [⌽𝐴ℋ↑=⌽↧√2n↑⌽↑Ψ↑](#47) | [p↑p=√[ñ/n↑]𝑃](#48)

[p↓p=𝑃/√[n↓ñ]](#49) | [&lt;ξₜ&gt;](#50) | [&lt;ξ²&gt;](#51) | [Results](#52) | 
<!-- TOC END -->

##<a name="1"></a> Expressions
This file is written in [Markdown](http://en.wikipedia.org/wiki/Markdown) format.
Proper mathematical [Expressions](http://en.wikipedia.org/wiki/Expression_%28mathematics%29)
will start with four spaces and end with either a newline or a pound sign, `#`.
Everything else is commentary.

Rules for expression than end with `=` and `→` which then continue on the next line are emerging, but
I haven't yet decided exactly what they are.

TODO: Convention on alphbet/letter use?
Complex/State function in capital greek.
Complex/Real numbers in lower case greek.
Integers in lower case latin.
I don't think I'm currently being consistent.

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
    u v w ≡ (u(vw))   # This is to disambiguate things like "Σ uv" which means "Σ[uv]", not "Σ[u]v".
    uvw ≡ ((uv)w)     # This is just the usual way we think of expressions.

    (⇤){(ᵛ),(ᵥ)}   # Superscripts and subscripts are left binding operators.
    (⇤){(!)}       # Factorial is a left binding operator.

    (⇥){(2),(½)}   # 2 and ½ bind right.  I don't think I use any other literal values.

    # Examples:
    u2vw = (u(2v))w
    u½vw = (u(½v))w
    u ½ v w = u(½(vw))
    u½ v w = (u½)(vw)   # But this would be weird, I would not write it this way.
    u!vw = ((u!)v))w

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
    ℤ{l}               # l is an Integer.

##<a name="6"></a> uᵥ
Subcripts labels a specific form of a more general expression:

    uᵥ[⋯]≡u[v,⋯]
    uₙₘ≡u[n,m,⋯]

Sequences can be thought of the set `{uₙ}`, but in this "paper", `uₙ` is always a well defined expression.

##<a name="7"></a> Π
Products of sequences, [`Π`](http://en.wikipedia.org/wiki/Multiplication#Capital_Pi_notation):

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

    ℚ{u},|u|≡(u>0)?u:-u

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

##<a name="13"></a> Arrow operators
Arrow Operators on subscripts:

    uᵥ↑ ≡ uᵥ₊₁
    uᵥ↓ ≡ uᵥ₋₁

    uᵥ⇈ ≡ uᵥ↑↑
    uᵥ⇈ = uᵥ₊₂

    uᵥ⇊ ≡ uᵥ↓↓
    uᵥ⇊ = uᵥ₋₂

    Σᵥu↑ ≡ Σᵥuᵥ₊₁   # Where context allows, subscript not needed.

    u↥ ≡ u₀↑   # Step up from "ground", just to make notation "pretty" later on.
    u↥ = u₁

    u↧ ≡ u₀↓   # Step down from "ground".
    u↧ = u₋₁

##<a name="14"></a> Σu↑

    Σₙuₙ = +u₀ + Σₙuₙ₊₁ - u[N]
    Σₙuₙ = +u₀ + Σₙu↑ - u[N]

    Σuₙ = u₀ + Σu↑

##<a name="15"></a> Σu↓

    Σₙuₙ = -u₋₁ + Σₙuₙ₋₁ + u[M]
    Σₙuₙ = -u₋₁ + Σₙu↓ + u[M]

    Σuₙ = -u₋₁ + Σu↓

##<a name="16"></a> ∑
This is interesting.
Looks like I'm going to have to argue `∑` over `ℤ` vs. `Σ` over `ℕ`.
Summation over ℤ indeces:

    ∑uₗ ≡ ⋯ + u₋₂ + u₋₁ + u₀ + u₁ + u₂ + ⋯
    ∑ₗuₗ ≡ Σ[-M,M]{l|uₗ}   # Halting version of ∑

    ∑ₗ1 = 2M+1 = 2N-1

The argument later will sound like a state can be created from "nothing" and destroyed to "nothing"...
as long as "What!?"

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
For the following examples, I use fatorial N! and exponential function e[N]:

    𝐿[u+1/N²] = u
    𝐿[u+e[N]/N!] = u    # Try N≥10.
    𝐿[u+(v^N)/N!] = u   # N depends on v, but for some N it's true.
    𝐿[u+e[-N]] = u      # Obviously, I hope.

    |u| ≤ 1/N, |v| ≤ 1/N  ⇒  |uv| ≤ 1/N², 𝐿[uv]=0

The Float::EPSILON for Ruby on my machine is about 2.22e-16.
So `𝐿` puts a limit on N on my machine of about 6.71e+7 (2.22e-16 ~ 1/(6.71e+7)^2).

## uₒ≡Σuₙ
I'll use subcript o, `ₒ`, to refer to the object that represents an infinite sum.

    uₒ≡Σuₙ

##<a name="20"></a> ℝ
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

##<a name="21"></a> ℂ
Complex numbers:

    ℂ ≡ (ℝ,ℝ)
    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)+(vᵣ,vᵢ)≡(uᵣ+vᵣ,uᵢ+vᵢ)
      (uᵣ,uᵢ)(vᵣ,vᵢ)≡(uᵣvᵣ-uᵢvᵢ,uᵣvᵢ+uᵢvᵣ)
      (uᵣ,uᵢ)(uᵣ,uᵢ)=(uᵣ²-uᵢ²,2uᵣuᵢ)
      uᵣ≡(uᵣ,0)
    ℂ{α,β}

##<a name="22"></a> i
The Imaginary number i:

    i ≡ (0,1)
    i² = (-1,0)
    # Proof
      (0,1)(0,1)
      (0²-1²,0×1+1×0)
      (-1,0)
    (u,v) = u+iv
    i² = -1

##<a name="23"></a> *
Complex conjugation:

    (u,v)* ≡ (u,-v)                  # Think * means multiplication?  Go to the beginning where I define ≡.
    (u+iv)* = u-iv
    e[i]* = (C+iS)* = C-iS = e[-i]   # what it does to e

    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)*(vᵣ,vᵢ)=(uᵣvᵣ+uᵢvᵢ,uᵣvᵢ-uᵢvᵣ)
      (uᵣ,uᵢ)*(uᵣ,uᵢ)=(u²ᵣ+v²ᵢ,0)
      (uᵣ,0)*(vᵣ,0)=(uᵣvᵢ,0)
      uᵣ*vᵣ=uᵣvᵣ   # Notice how the it does end up looking like multiplication in ℝ.

      # Just to review
      (uᵣ,uᵢ)×(vᵣ,vᵢ) = (uᵣvᵣ-uᵢvᵢ, uᵣvᵢ+uᵢvᵣ)
      (uᵣ,uᵢ)×(uᵣ,uᵢ) = (u²ᵣ-u²ᵢ, 2uᵣuᵢ)
      (uᵣ,uᵢ)*(vᵣ,vᵢ) = (uᵣvᵣ+uᵢvᵢ, uᵣvᵢ-uᵢvᵣ)
      (uᵣ,uᵢ)*(uᵣ,uᵢ) = (u²ᵣ+u²ᵢ, 0)

##<a name="24"></a> &lt;u&gt;
Dirac notation:

    <αu|βu> ≡ ΣΣ (αuₙ)*(βuₘ)
    <αu|βu> = α*<u|βu> = β<αu|u>
    <αu|βu>* = <βv|αu>
    <αu| + <βv| = <αu+βv|

    <u> ≡ <u|u>

    <αu> = α*α<u>
    # Proof
      <αu>
      <αu|αu>
      α*<u|αu>
      α*α<u|u>
      α*α<u>

    |ₙ> ≡ |uₙ>   # where u is know from context

    <u|ₗ> = uₗ*uₗ
    # Proof
      <u|ₗ>
      <u|uₗ>
      ΣΣ uₙ*uₗ
      uₗ*uₗ   # uₙ are orthogonal, only the l term contributes

    <uₗ> = uₗ*uₗ
    <u|ₗ> = <uₗ>
    <α> = α*α
    # TODO: What we mean by average value,  <u> ≡ Σₙuₙ/N ?

##<a name="25"></a> n!
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

##<a name="26"></a> nᵥ
I'd like to make the following refinement in ℕ,
[Factoral](http://www.urbandictionary.com/define.php?term=Factoral&defid=5895569) forward:

    # START SCRATCH
    Ƒ⁰ₙ ≡ 1
    Ƒᵐₙ ≡ (n+m)Ƒᵐ⁻¹n


    Ƒ¹ₙ = (n+1)Ƒ⁰ₙ = (n+1)
    Ƒ²ₙ = (n+2)Ƒ¹ₙ = (n+2)(n+1)
    Ƒ³ₙ = (n+3)Ƒ²ₙ = (n+3)(n+2)(n+1)
    Ƒ⁴ₙ = (n+4)(n+3)(n+2)(n+1)
    # ...

    Ƒᵐ⁺¹ₙ = (n+m+1)Ƒᵐₙ
    Ƒᵐ⁺¹ₙ/(n+m+1) = Ƒᵐₙ
    Ƒᵐₙ = Ƒᵐ⁺¹ₙ/(n+m+1)

    Ƒ²ₙ = Ƒ³ₙ/(n+3) = (n+3)(n+2)(n+1)/(n+3) = (n+2)(n+1)
    Ƒ¹ₙ = Ƒ²ₙ/(n+2) = (n+2)(n+1)/(n+2) = n+1
    Ƒ⁰ₙ = Ƒ¹ₙ/(n+1) = (n+1)/(n+1) = 1
    Ƒ⁻¹ₙ = Ƒ⁰ₙ/(n) = 1/n
    Ƒ⁻²ₙ = Ƒ⁻¹ₙ/(n-1) = 1/(n(n-1))
    Ƒ⁻³ₙ = Ƒ⁻²ₙ/(n-2) = 1/(n(n-1)(n-2))
    Ƒ⁻⁴ₙ = Ƒ⁻³ₙ/(n-3) = 1/(n(n-1)(n-2)(n-3))

    Ƒ₁n = 1×2×3×...×n
    Ƒ₂n = 2×3×⋯×n

    A^3
    A³ # :superscript
    A² # :superscript
    A⁰ # :superscript
    A¹ # :superscript
    Ƒ⁰n
    n'⁰ ≡ 1
    n'¹ = n+1
    n'² = (n+1)(n+2)
    n!  = 1×2×3×...×n
    Ƒ²n = (n+1)(n+2)

    Ƒⁿ₀ = (0+1)...(0+n) = n!

    Ƒ¹ₙƑⁿ₁ = Ƒⁿ⁺¹₁
    Ƒ³₂Ƒ³₁ = (2+1)(2+2)(2+3) (1+1)(1+2)(1+3) = 3*4*5 * 2*3*4 = 2 (3*4)² * 5 = Ƒ¹₁(Ƒ²₂)²Ƒ¹₄
    Ƒ³₂Ƒ³₁ = Ƒ¹₁(Ƒ²₂)²Ƒ¹₄

    (ⁿₘ) ≡ n!/(m!(n-m)!)
    (³₂) = 3!/(2!(3-2)!) = 6/2.1 = 3

    Ƒ³₂ = 3.4.5 = 12.5 = 60
    Ƒ³₂ = 5!/2!
    Ƒᵐₙ = (m+n)!/n!
    Ƒ⁰ₙ = (0+n)!/n! = n!/n! = 1

    ƒ = 1/Ƒ
    ƒ¹ₙ = 1/(n+1)
    ƒ⁻¹ₙ = n

    nᵥ ≡ Ƒᵛₙ   # I'm going to be changing notation to Ƒᵛₙ, but currently things are written as nᵥ.
    # END SCRATCH

    nᵥ ≡ nᵥ₋₁(n+v)
    n₀ ≡ 1

    n₁ = n₀(n+1)
    n₁ = n+1

    n₂ = n₁(n+2)
    n₂ = (n+1)(n+2)

    n₃ = n₂(n+3)
    n₃ = (n+1)(n+2)(n+3) # and so on...

    4₂ = (4+1)(4+2) = 5×6 = 30   # For example.

Factoral backwards:

    nᵥ₋₁ = nᵥ/(n+v)
    nᵥ = nᵥ₊₁/(n+v+1)

    n₋₁ = n₀/(n-1+1) = 1/n
    n₋₁ = 1/n

    n₋₂ = n₋₁/(n-2+1) = (1/n)/(n-1)
    n₋₂ = 1/(n(n-1))

    n-₃ = n₋₂/(n-3+1) = (1/(n(n-1)))/(n-2)
    n-₃ = 1/(n(n-1)(n-2)) # and so on...

    4₋₂ = 1/(4(4-1)) = 1/(4×3) = 1/12   # For example.

Arrows meaningful as Factorals:

    n⇈ = (n+1)(n+2)
    n↑ = n+1
    n₀ = 1
    n↓ = 1/n
    n⇊ = 1/(n(n-1))

##<a name="27"></a> nᵥn!
Factoral with Factorial:

    nᵥn! = (n+v)!

    n₃n! = (n+1)(n+2)(n+3)n! = (n+3)!   # OK

    n-₃n! = n!/(n(n+1)(n+2))
    n-₃n! = (n-3)!(n-2)(n-1)n/(n(n-1)(n-2))
    n-₃n! = (n-3)!   # OK

    n↑n! = (n+1)!
    n↓n! = (n-1)!

    n⇈n! = (n+2)!
    n⇊n! = (n-2)!

##<a name="28"></a> (ⁿₘ)
[Binomial coefficient](http://en.wikipedia.org/wiki/Binomial_coefficient),
n choose m:

    (ⁿₘ) ≡ n!/(m!(n-m)!)

    (ⁿₘ) = 1/(n-ₘm!)
    # Proof
      (ⁿₘ)
      n!/(m!(n-m)!)
      n!/(m!n!n-ₘ)
      1/(m!n-ₘ)

##<a name="29"></a> Sine, Cosine, and Exponential
[Trigonometric](http://en.wikipedia.org/wiki/Trigonometric_functions#Series_definitions) and
[Exponential](http://en.wikipedia.org/wiki/Exponential_function#Formal_definition)
functions series definitions:

    :Sine[u] ≡ Σ (-1)ⁿ u^(2n+1) / (2n+1)!
    S[u] ≡ :Sine[u]

    :Cosine[u] ≡ Σ (-1)ⁿ u^(2n) / (2n)!
    C[u] ≡ :Cosine[u]

    :Exponential[u] ≡ Σ uⁿ / n!
    e[u] ≡ :Exponential[u]
    eᵘ ≡ e^(u) ≡ e[u]   # Alternate forms.

[Trigonometric Identities](http://en.wikipedia.org/wiki/List_of_trigonometric_identities):

    S²+C²=1            # Pythagoras
    S[u+v]=SuCv+CuSv   # Sine's angle sum
    C[u+v]=CuCv-SuSv   # Cosine's angle sum
    C[2u]=1-2S²u       # Cosine double angle "cos(2u)=1-2sin²(u)"

Just a quick exercise.
Derivation: Cosine's Angle Sum to Cosine Double Angle:

    :Cosine[2u]
    C[2u] = C[2u]
    C[2u] = C[u+u]
    C[2u] = C[u]C[u]-S[u]S[u]
    C[2u] = CuCu-SuSu   # Shorten form
    C[2u] = CC-SS   # From context, C=:Cosine[u] and S=:Sine[u]
    C[2u] = C²-S²
    C[2u]-1 = C²-S²-1
    C[2u]-1 = (C²-1)-S²
    C[2u]-1 = (-S²=C²-1)-S²   # A bit of "rubyism" here.  Just invoking Pythagoras.
    C[2u]-1 = -S²-S²
    C[2u]-1 = -2S²
    C[2u] = 1-2S²   # I should expand out the context once the shorthand has fulfilled its purpose.
    C[2u] = 1-2S²[u]
    :Cosine[2u] = 1 - 2:Sine²[u]

Known properties of e:

    e[u]e[v] = e[u+v]
    e[iu] = C[u]+iS[u]
    e[-iu] = C[u]-iS[u]
    e[0] = 1

##<a name="30"></a> Δ²
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

##<a name="31"></a> 𝑃ₙ
`𝑃` is the [Poisson distribution](http://en.wikipedia.org/wiki/Poisson_distribution):

    𝑃ₙ ≡ uⁿe[-u]/n!
    Σ 𝑃ₙ = 1
    0 ≤ 𝑃ₙ ≤ 1
    <u> = Σ 𝑃ₙuₙ

##<a name="32"></a> pₙ

    pₙ ≡ √[uⁿe[-u]/n!]
    pₙ*pₙ = 𝑃ₙ
    # Proof
      pₙ*pₙ
      √[uⁿe[-u]/n!]*√[uⁿe[-u]/n!]
      √[uⁿe[-u]/n!]√[uⁿe[-u]/n!]   # It's just all real.
      uⁿe[-u]/n!
      𝑃ₙ

##<a name="33"></a> Fundamental values
I think the point here is that these values are "measured" by "experiment" in "some way".

    ℝ{m}   # Mass
    ℝ{k}   # Spring contant 

What about π ?
You can check that there exist several series 
of rational terms that produce [π](http://en.wikipedia.org/wiki/Pi):

    ℝ{π} ← π = 4 Σ (-1)ⁿ/(2n+1) # http://en.wikipedia.org/wiki/Leibniz_formula_for_π
    # Proof:
      π
      4 Σ (-1)ⁿ/(2n+1)
      4 Σ 1/(2(2n)+1) - 1/(2(2n+1)+1)                              # pairing the alternating series
      4 Σ 1/(4n+1) - 1/(4n+3)
      4 Σ ((4n+3)-(4n+1))/((4n+1)(4n+3))
      4 Σ 2/((4n+1)(4n+3))
      Σ 8/((4n+1)(4n+3))
        |8/((4n+1)(4n+3))| ≤ |8/(16n²)| ≤ |1/(2n²)| ≤ 1/n² ← n≥N   # Fits given definition of ℝ.

##<a name="34"></a> Derived values

    ω² ≡ k/m   # Angular frequency
    ω = √[k/m]

    f ≡ ω/(2π)   # Frequency

TODO: need to explain ħ.

    Eₙ = ωħ(n+½)   # 3.2: Energy eigen-value

##<a name="35"></a> ⌽ᵗₙ
7.17 TODO: why -iEₙt/ħ and not +iEₙt/ħ?
Time evolution:

    ⌽ᵗₙ ≡ e[-iω(n+½)t] = e[-iEₙt/ħ]   # NOTE! The ½ part makes this object a bit of a screw ball.
    φᵗₙ ≡ e[-iωnt]                    # "How do we end up with this?" you may ask.

    ⌽ₙ*⌽ₘ = φₘ-ₙ   # You don't have to explicitly show time if it can be infered.
    # Proof:
      ⌽ₙ*⌽ₘ
      ⌽-ₙ⌽ₘ
      e[iω(n+½)t - iω(m+½)t]
      e[-iω(m-n)t]
      φₘ-ₙ

    # Don't have to explicitly show quantum number if it can be infered.
    ⌽⁰ = 1
    ⌽¹ = e[-iω(n+½)]
    ⌽ᵗ = (⌽¹)^t = e[t × (-iω(n+½))] = e[-iω(n+½)t]   # Just to show that the notation makes sense.

##<a name="36"></a> ⌽→φ

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

    φₙ = cₙ-isₙ   # φ in terms of c and s.

    φ₁ = c₁-is₁

    φ₋₁ = c₁+is₁   # Maybe that'll work.

    φ₁ + φ₋₁ = 2c₁
    φ↥ + φ↧ = 2c₁   # Remember this one!

    φ₁ - φ₋₁ = 2s₁
    φ↥ - φ↧ = 2s₁

    φ₂ = c₂-is₂
    φ₋₂ = c₂+is₂

    φ₋₂ + φ₂ = 2c₂
    φ↧↓ + φ↥↑ = 2c₂   # And remember this one!

##<a name="37"></a> ñ
Average Quantum number ñ

    <n> = <n|pₙ*npₙ|m> = Σ npₙpₙ = Σ n𝑃ₙ   # only n=m terms contribute

    ñ ≡ 𝐿 <n>
    ñ = 𝐿 Σ n𝑃ₙ = 𝐿 Σₙ n𝑃ₙ   # Remember that 𝐿 truncates the series.

    Σₙ n𝑃ₙ = 𝐿 Σₙ nuⁿe[-u]/n!                    # Just by definition of 𝑃ₙ.
     = Σ[0,M]{n|nuⁿe[-u]/n!}                     # Definition of Σₙ.
     = 0 + Σ[1,M]{n|nuⁿe[-u]/n!}                 # The first element in the series is just zero.
     = Σ[1,M]{n|uⁿe[-u]/(n-1)!}                  # Have the n factor absorbed by the factorial.
     = Σ[0,M-1]{n|u[n+1]e[-u]/n!}                # Shift.
     = uΣ[0,M-1]{n|uⁿe[-u]/n!}                   # Take out a factor of u.
     = u(Σ[0,M]{n|uⁿe[-u]/n!} - (u^M)e[-M]/M!)   # Add and subtract the an Nth element (which is M).
     = u(Σₙ𝑃ₙ) - u(u^M)e[-M]/M!                  # Definition of Σₙ and 𝑃ₙ.
     = u(1) - u^(M+1)e[-M]/M!                    # Poisson distribution sums up to one.
     = u - u^(M+1)e[-M]/M!

    ñ = 𝐿[u - u^(M+1)e[-M]/M!]
    ñ = 𝐿[u] - 𝐿[u^(M+1)e[-M]/M!]
    ñ = u - 0
    ñ = u   # As expected.  :)

##<a name="38"></a> 𝐿 Σ[n(n-1)𝑃ₙ]

    𝐿 Σ n(n-1)𝑃ₙ
    𝐿 Σₙ n(n-1)𝑃ₙ
    𝐿 Σₙ 1/n₋₂ uⁿe[-u]/n!
    𝐿 Σₙ uⁿe[-u]/(n-2)!
    𝐿 Σₙ u² u^(n-2)e[-u]/(n-2)!
    𝐿 u² Σₙ u^(n-2)e[-u]/(n-2)!
    𝐿 u² Σ[0,M]{n|u^(n-2)e[-u]/(n-2)!}
    𝐿 u² Σ[-2,M-2]{n|uⁿe[-u]/n!}
    𝐿 u² (Σ[-2,-1]{n|uⁿe[-u]/n!} + Σ[0,M-2]{n|uⁿe[-u]/n!})
    𝐿 u² (Σ[-2,-1]{n|uⁿe[-u]/n!} + Σ[0,M-2]{n|𝑃ₙ})
    u²(𝐿[e[-u]/(u²(-2)!)] + 𝐿[e[-u]/(u(-1)!)] + 𝐿[Σ[0,M-2]{n|𝑃ₙ}])
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

    𝑃ₙ = ñⁿe[-ñ]/n!
    pₙ = √[ñⁿe[-ñ]/n!]

##<a name="39"></a> p→𝑃

    pₙpₙ₊₁ = √[ñⁿe[-ñ]/n!] √[ñⁿ⁺¹e[-ñ]/(n+1)!]
           = √[ñⁿe[-ñ]/n!] √[ñⁿe[-ñ]/n!] √[ñ/(n+1)] 
           = pₙ pₙ √[ñ/(n+1)] 
           = 𝑃ₙ √[ñ/(n+1)] 
           = √[ñ/(n+1)]𝑃ₙ 
    pₙpₙ₊₁ = √ñ𝑃ₙ/√n₁   # Using Factoral
    pp↑ = √ñ𝑃ₙ/√n↑      # And Arrow notation

    pₙpₙ₋₁ = √[ñⁿe[-ñ]/n!] √[ñⁿ⁻¹e[-ñ]/(n-1)!]
           = √[ñⁿe[-ñ]/n!] √[ñⁿe[-ñ]/n!] √[n/ñ] 
           = pₙ pₙ √[n/ñ] 
           = 𝑃ₙ √[n/ñ] 
           = √[n/ñ]𝑃ₙ 
    pₙpₙ₋₁ = 𝑃ₙ/√[ñn₋₁]   # Using Factoral
    pp↓ = 𝑃ₙ/√[ñn↓]       # And Arrow notation

    pₙpₙ₊₂ = √[ñⁿe[-ñ]/n!] √[ñⁿ⁺²e[-ñ]/(n+2)!]
           = √[ñ²/((n+1)(n+2))] √[ñⁿe[-ñ]/n!] √[ñⁿe[-ñ]/n!]
           = ñ/√[(n+1)(n+2)] pₙpₙ
           = ñ/√[(n+1)(n+2)] 𝑃ₙ
    pₙpₙ₊₂ = ñ𝑃ₙ/√n₂   # Using Factoral
    pₙpₙ₊₂ = ñ𝑃ₙ/√n⇈   # Using Arrow

    pₙpₙ₋₂ = √[ñⁿe[-ñ]/n!] √[ñⁿ⁻²e[-ñ]/(n-2)!]
           = √[(n-1)n/ñ²] √[ñⁿe[-ñ]/n!] √[ñⁿe[-ñ]/n!]
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

##<a name="40"></a> ξ
The non-dimensional displacement, ξ.

    ξ² ≡ mω/ħ x²   # A.1b
    x² = ħ/(mω) ξ²

##<a name="41"></a> 𝐴ₙ
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

##<a name="42"></a> ℋₙ
The Hermite polynomial:

    ℋₙ[ξ] ≡ (-1)ⁿ e[ξ²] Dᵧⁿ e[-ξ²]   # A.3, this is "physicists' Hermite polynomials" in Wikipedia.

    Dᵧ ℋₙ[ξ] = 2nℋₙ₋₁[ξ]   # A.4a
    # Proof:
      # It's actually a well known property of ℋ.
      # In my notes I review a proof by genetating function... unreadable to me now.
      # But found this elegant proof online,
      # http://math.stackexchange.com/questions/581897/hermite-polynomials-recurrence-relation:
      D ℋₙ[ξ]                                           # Given
      D[(-1)ⁿ e[ξ²] Dⁿ e[-ξ²]]                          # Substitution, definition of ℋ
      (-1)ⁿ D[e[ξ²] Dⁿ e[-ξ²]]                          # Take out the constant
      (-1)ⁿ (D[e[ξ²]] Dⁿ e[-ξ²] + e[ξ²] D[Dⁿ e[-ξ²]])   # Product rule
      (-1)ⁿ (D[e[ξ²]] Dⁿ e[-ξ²] + e[ξ²] Dⁿ D[e[-ξ²]])   # Well... obviously we're going to do that!
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²] Dⁿ -2ξe[-ξ²])    # Executing D
      # I don't remember ever coming across the General Leibniz rule
      # http://en.wikipedia.org/wiki/General_Leibniz_rule
      # Let (ⁿₘ) mean n choose m.
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²] Σ[0,n]{m| (ⁿₘ) Dᵐ[-2ξ] Dⁿ-ᵐe[-ξ²]})   # General Leibniz rule
      # D²[-2ξ]=0, Dⁿ[-2ξ]=0 if n>1.
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²] Σ[0,1]{m| (ⁿₘ) Dᵐ[-2ξ] Dⁿ-ᵐe[-ξ²]})
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²]((ⁿ₀) D⁰[-2ξ] Dⁿ-⁰e[-ξ²] + (ⁿ₁) D¹[-2ξ] Dⁿ⁻¹e[-ξ²])
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²](   1 D⁰[-2ξ] Dⁿ  e[-ξ²] +    n D¹[-2ξ] Dⁿ⁻¹e[-ξ²])
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²](         -2ξ  Dⁿ  e[-ξ²] +     n   (-2)  Dⁿ⁻¹e[-ξ²])
      (-1)ⁿ (2ξe[ξ²]Dⁿe[-ξ²] - 2ξe[ξ²]Dⁿe[-ξ²] - 2ne[ξ²]Dⁿ⁻¹e[-ξ²])
      (-1)ⁿ (0 - 2ne[ξ²]Dⁿ⁻¹e[-ξ²])
      (-1)ⁿ (-2) ne[ξ²]Dⁿ⁻¹e[-ξ²]
      (-1)ⁿ⁻¹ 2 ne[ξ²]Dⁿ⁻¹e[-ξ²]
      2n (-1)ⁿ⁻¹ e[ξ²] Dⁿ⁻¹e[-ξ²]
      2n ℋₙ₋₁[ξ]

    ℋₙ₊₁[ξ] = 2ξℋₙ[ξ] - 2nℋₙ₋₁[ξ]   # A.4b
    # Also a well known property of ℋ, but here's a proof:
      ℋₙ₊₁[ξ]
      (-1)ⁿ⁺¹ e[ξ²] Dⁿ⁺¹ e[-ξ²]
      (-1)ⁿ(-1) e[ξ²] Dⁿ[D e[-ξ²]]
      (-1)ⁿ(-1) e[ξ²] Dⁿ[(-2ξ) e[-ξ²]]
      (-1)ⁿ     e[ξ²] Dⁿ[  2ξ  e[-ξ²]]
      (-1)ⁿ e[ξ²] Σₘ (ⁿₘ) Dᵐ[2ξ] Dⁿ-ᵐ[e[-ξ²]]                                  # General Leibniz rule
      (-1)ⁿ e[ξ²]((ⁿ₀) D⁰[2ξ] Dⁿ-⁰[e[-ξ²]] + (ⁿ₁) D¹[2ξ] Dⁿ⁻¹[e[-ξ²]] + 0 ⋯)   # Dejavu
      (-1)ⁿ e[ξ²](   1   (2ξ) Dⁿ  [e[-ξ²]] +    n   (2)  Dⁿ⁻¹[e[-ξ²]])
      (-1)ⁿ e[ξ²](2ξDⁿ[e[-ξ²]] + 2nDⁿ⁻¹[e[-ξ²]])
      (-1)ⁿ e[ξ²] 2ξDⁿ[e[-ξ²]] + (-1)ⁿ e[ξ²] 2nDⁿ⁻¹[e[-ξ²]])                   # Distribute
      2ξ (-1)ⁿ e[ξ²] Dⁿ[e[-ξ²]] + 2n (-1)ⁿ e[ξ²] Dⁿ⁻¹[e[-ξ²]])
      2ξ (-1)ⁿ e[ξ²] Dⁿ[e[-ξ²]] + 2n (-1)(-1)ⁿ⁻¹ e[ξ²] Dⁿ⁻¹[e[-ξ²]])
      2ξ (-1)ⁿ e[ξ²] Dⁿ[e[-ξ²]] - 2n (-1)ⁿ⁻¹ e[ξ²] Dⁿ⁻¹[e[-ξ²]])
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

##<a name="43"></a> Ψₙ
Please accept the EigenState of the Simple Harmonic Oscillator Ψₙ as given by Liboff's book in page 189.
The EigenState Ψₙ:

    Ψₙ[x] ≡ |n>
    Ψₙ[x] = 𝐴ₙℋₙ[ξ]e[-ξ²/2]

The State Function Ψ:

    Ψ[x] = Σ pₙ Ψₙ[x]   # TODO: or is it Σ 𝑃ₙ Ψₙ[x] ? Check Σ pₙ = 1 ?

The Problem To Be Solved

    Minimize:     <Ψ|n><n|ΔxΔp|m><m|Ψ>
    Subject to:   <Ψ|n><n|Eₙ|n><n|Ψ> = Eₒ

TODO: I just jumped from the above to the calculation of Δ²x !?
Will say something like ΣΣuₙvₘ = (Σuₙ)(Σvₙ)

##<a name="44"></a> ξΨₘ
Motivation: I will be calculating <Ψ|ξ|Ψ> later.

    ξΨₘ = ½𝐴ₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
    # Proof:
      ξΨₘ
      ξ𝐴ₘℋₘ[ξ]e[-ξ²/2]
      𝐴ₘ ξℋₘ[ξ]e[-ξ²/2]
      𝐴ₘ ½(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
      ½𝐴ₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))

##<a name="45"></a> &lt;ξ₀&gt;
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

##<a name="46"></a> ⌽𝐴ℋ↓/½n↓=⌽↥/√½n↓⌽↓Ψ↓

    ⌽𝐴ℋ↓/½n↓
    ⌽√[½n↓]𝐴↓ℋ↓/½n↓   # 𝐴=√[½n↓]𝐴↓
    ⌽𝐴↓ℋ↓/√[½n↓]
    ⌽↥⌽↓𝐴↓ℋ↓/√½n↓     # ⌽=⌽₁⌽↓
    ⌽↥/√½n↓ ⌽↓𝐴↓ℋ↓
    ⌽↥/√½n↓ ⌽↓Ψ↓

##<a name="47"></a> ⌽𝐴ℋ↑=⌽↧√2n↑⌽↑Ψ↑

    ⌽𝐴ℋ↑
    ⌽√2n↑𝐴↑ℋ↑   # 𝐴=√[2n↑]𝐴↑
    ⌽↧⌽↑√2n↑𝐴↑ℋ↑
    ⌽↧⌽↑√2n↑𝐴↑ℋ↑
    ⌽↧√2n↑ ⌽↑𝐴↑ℋ↑
    ⌽↧√2n↑ ⌽↑Ψ↑

##<a name="48"></a> p↑p=√[ñ/n↑]𝑃

    p↑p
    √[ñⁿ⁺¹e[-ñ]/(n+1)!] p
    √[ñ/(n+1) ñⁿe[-ñ]/n!] p
    √[ñ/(n+1)]p p
    √[ñ/(n+1)]𝑃
    √[ñ/n₁]𝑃
    √[ñ/n↑]𝑃

##<a name="49"></a> p↓p=𝑃/√[n↓ñ]

   p↓p
    √[ñⁿ⁻¹e[-ñ]/(n-1)!] p
    √[(n/ñ) ñe[-ñ]/n!] p
    √[n/ñ] p p
    √[1/(n₋₁ñ)]𝑃
    𝑃/√[n₋₁ñ]
    𝑃/√[n↓ñ]

##<a name="50"></a> &lt;ξₜ&gt;
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

##<a name="51"></a> &lt;ξ²&gt;
TODO: `<ξ²>`:

    # And who wants to work with this mess?
    <ξ²> = (ñ+½) +
      ½Σ e[-iω(n+½)t]* √[uⁿe[-u]/n!] (
        e[-iω((n-2)+½)t] √[n(n-1)] √[u^(n-2)e[-u]/(n-2)! +
        e[-iω((n+2)+½)t] √[(n+1)(n+2)] √[u^(n+2)e[-u]/(n+2)!
      )
    <ξ²> = (ñ+½) + ½Σ ⌽ₙ*pₙ* (⌽ₙ₋₂√[n(n-1)]pₙ₋₂ +  ⌽ₙ₊₂√[(n+1)(n+2)]pₙ₊₂)   # 7.21
    # And much nicer...
    <ξ²> = (ñ+½) + ½Σ ⌽*p (⌽⇊/√n⇊ p⇊ +  ⌽⇈√n⇈ p⇈)                           # pretty noted
    <ξ²> = (ñ+½) + ½Σ ⌽*⌽⇊/√n⇊ pp⇊ +  ⌽*⌽⇈√n⇈ pp⇈                           # Distribute
    <ξ²> = (ñ+½) + ½Σ φ↧↓/√n⇊ pp⇊ +  φ↥↑√n⇈ pp⇈                             # ⌽→φ
    <ξ²> = (ñ+½) + ½Σ φ↧↓/√n⇊ 𝑃/(ñ√n⇊) +  φ↥↑√n⇈ ñ𝑃/√n⇈                   # p->𝑃
    <ξ²> = (ñ+½) + ½Σ φ↧↓/n⇊ 𝑃/ñ +  φ↥↑ ñ𝑃                                # Simplify
    <ξ²> = (ñ+½) + ½Σ φ↧↓ n(n-1) 𝑃/ñ +  φ↥↑ ñ𝑃                            # 1/n⇊ = n(n-1)
    <ξ²> = (ñ+½) + ½(Σ[φ↧↓ n(n-1) 𝑃/ñ] +  Σ[φ↥↑ ñ𝑃])                      # Separate sums
    <ξ²> = (ñ+½) + ½(φ↧↓/ñΣ[n(n-1)𝑃] +  φ↥↑ñΣ[𝑃])                         # Take out the constants
    <ξ²> = (ñ+½) + ½(φ↧↓/ñ(ñ²) +  φ↥↑ñ(1))                               # Evaluate sums
    <ξ²> = (ñ+½) + ½(φ↧↓ñ + φ↥↑ñ)                                         # Simplify
    <ξ²> = (ñ+½) + ½ñ(φ↧↓ + φ↥↑)
    <ξ²> = (ñ+½) + ½ñ(2c₂)                                                 # Remember?  φ↧↓+φ↥↑=2c₂.
    <ξ²> = (ñ+½) + ñc₂
    <ξ²> = (ñ+½) + ñ(1-2s²₁)                                               # Double angle, c₂=1-2s²₁
    <ξ²> = (ñ+½) + ñ- 2ñs²₁
    <ξ²> = 2ñ + ½ - 2ñs²₁
    <ξ²> = ½ + 2ñ - 2ñs²₁
    <ξ²> = ½ + 2ñ(1 - s²₁)
    <ξ²> = ½ + 2ñc²₁                                                        # Pythagoras
    <ξ²> = ½ + 2ñ:Cosine²[nwt]

##<a name="52"></a> Results
7.5 Results:

    Δ²ξ = <ξ²> - <ξ>²
        = (½ + 2ñc²₁) - 2ñc²₁
        = ½

## Resources
On top of the references given in the appendix, I'd like to add the following resources:

* njwildberger's [MathFoundations](https://www.youtube.com/playlist?list=PL5A714C94D40392AB)
* Stanford's Susskind's [Advanced Quantum Mechanics](https://www.youtube.com/playlist?list=PLpGHT1n4-mAsmMxmSX0LCaXIXT2PmU85m)

So the way it works is that any mistakes herein are all my fault.
If I say anything good, it's because of these other people:
