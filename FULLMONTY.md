[CONTENTS](CONTENTS.md)

# The Full Monty
Here I write explicitly all my work, as if writting computer code.
Consider all symbols to have global scope.
Each symbol should only be defined once, except `u` and `v` which will be used as temporary general variables.
In books you'll see `sin²(x)` to mean `sin(x)*sin(x)`.
I'll use that convention in general.
`u²[v]` will mean `u[v]*u[v]` and not `u[u[v]]`.
The initial part of this section goes over elementary material, but
it's a good warmup and demonstrates my notation.

> This section was not in the original thesis.
> Because I have UTF-8 available, I'll try to better match the expected notation.
> I've switched  notation 
> for the time development from `1ₙ` to `Φₙ`,
> for the non-dimensional displacement from `y` to `ξ`,
> for the Dirac notation from `<n]` to `<n|`, and
> for the variance(uncertainty) operator from `d²` to `Δ²`.
> Eventually I hope to have the entire work in one stream of "mathematical code".
> Please use github to contact me to let me know of any errors (of any type).

<!-- TOC START -->
### Sections:

[Expressions](#1) | [{u,v,w}](#2) | [Precedence rules](#3) | [ℕ](#4) | [ℤ and ℚ](#5) | [uᵥ](#6) | [Π](#7) | [uᵛ](#8)

[√u](#9) | [|u|](#10) | [Σ](#11) | [Arrow operators](#12) | [Limit function](#13) | [ℝ](#14) | [ℂ](#15) | [i](#16)

[†](#17) | [&lt;u&gt;](#18) | [n!](#19) | [nᵥ](#20) | [(ⁿₘ)](#21) | [Sine, Cosine, and Exponential](#22) | [Δ²](#23) | [Pₙ](#24)

[pₙ](#25) | [Fundamental values](#26) | [Derived values](#27) | [Φᵗₙ](#28) | [Φ→φ](#29) | [nᵒ](#30) | [L Σ[n(n-1)Pₙ]](#31) | [p→P](#32)

[ξ](#33) | [Aₙ](#34) | [ℋₙ](#35) | [Ψₙ](#36) | [ξΨₘ](#37) | [&lt;ξ₀&gt;](#38) | [ΦAℋ↓/½n↓=Φ↥/√½n↓Φ↓Ψ↓](#39) | [ΦAℋ↑=Φ↧√2n↑Φ↑Ψ↑](#40)

[p↑p=√[nᵒ/n↑]P](#41) | [p↓p=P/√[n↓nᵒ]](#42) | [&lt;ξₜ&gt;](#43) | [&lt;ξ²&gt;](#44) | [Results](#45) | 
<!-- TOC END -->

##<a name="1"></a> Expressions
This file is written in [Markdown](http://en.wikipedia.org/wiki/Markdown) format.
Proper mathematical [Expressions](http://en.wikipedia.org/wiki/Expression_%28mathematics%29)
will start with four spaces and end with either a newline or a pound sign, `#`.
Everything else is commentary.


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
For example, √2πx is √[2π]x, but √nπx is √[n]πx.

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

##<a name="7"></a> Π

    # 1.upto(m).inject(1){|v,n|v*u[n]}
    Π[1,0] ≡ 1
    Π[1,m]{n|uₙ} ≡ u₁*u₂*⋯*uₙ-₁*uₙ*uₙ+₁*⋯*uₘ-₁*uₘ
    Π[1,2]{u} = u*u
    Π[1,3]{n|n} = 1*2*3

##<a name="8"></a> uᵛ
Superscripts normally are ℕ denoting repetition:

    uⁿ ≡ Π[1,n]{u}
    u⁰=1
    uⁱ=u
    u²=uu    # Square
    u³=uuu   # Cube

    uⁿ[v] ≡ (u[v])ⁿ
    u²[v] ≡ u[v]*u[v]   # For example: "sin²(x) = sin(x)*sin(x)"
    uᵐₙ ≡ (uₙ)ᵐ         # I'm leaving uₙ² undefined, but it's probably u[n²].

Superscripts also denotes power or raising operations:

    uᵛ ≡ u^v   # or "u**v"

##<a name="9"></a> √u
Squareroot:

    √[u²]≡u
    √[uu]=u

##<a name="10"></a> |u|
Absolute value:

    ℚ{u},|u|≡(u>0)?u:-u

##<a name="11"></a> Σ
Summation over indeces:

    Σuₙ ≡ u₀ + u₁ + u₂ + ⋯   # Non-halting series.
    ΣΣuₙₘ ≡ (u₀₀ + u₀₁ + u₀₂ + ⋯) + (u₁₀ + u₁₁ + u₀₂ + ⋯) + (u₂₀ + u₂₁ + u₂₂ + ⋯) + ⋯

    Σₙuₙ ≡ Σ[0,M]{n|u[n]}   # NOTE!  Series indeces start with zero.
    ΣₙΣₘuₙₘ ≡ Σ[0,M]{n| Σ[0,M]{m| u[n,m]}}

    N = Σₙ 1

##<a name="12"></a> Arrow operators
Arrow Operators on subscripts:

    uᵥ↑ ≡ uᵥ+₁
    uᵥ↓ ≡ uᵥ-₁

    uᵥ⇈ ≡ uᵥ↑↑
    uᵥ⇈ = uᵥ+₂

    uᵥ⇊ ≡ uᵥ↓↓
    uᵥ⇊ = uᵥ-₂

    Σᵥu↑ ≡ Σᵥuᵥ+₁   # Where context allows, subscript not needed.

    u↥ ≡ u₀↑   # Step up from "ground", just to make notation "pretty" later on.
    u↥ = u₁

    u↧ ≡ u₀↓   # Step down from "ground".
    u↧ = u-₁

##<a name="13"></a> Limit function
N is very, very, big!
I want try to keep things simple and
avoid a full treatment of limits.
Let's try a simple limit function:

    L Σuₙ ≡ L Σₙuₙ               # L truncates the series to down to N elements.
    L[u+v] ≡ L[u] + L[v]
    L[u] ≡ (|u| ≥ 1/N²)? u : 0   # L ignores very small numbers.

    L Σₙ[1/N] = Σₙ L[1/N]
      = Σₙ[1/N]
      = 1   # Notice that this would have been 0 had I set the threshold to ≥ 1/N.

    L Σₙ[1/N²] = Σₙ L[1/N²]
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

    L[u+1/N²] = u
    L[u+e[N]/N!] = u    # Try N≥10.
    L[u+(v^N)/N!] = u   # N depends on v, but for some N it's true.
    L[u+e[-N]] = u      # Obviously, I hope.

    |u| ≤ 1/N, |v| ≤ 1/N  ⇒  |uv| ≤ 1/N², L[uv]=0

The Float::EPSILON for Ruby on my machine is about 2.22e-16.
So "L" puts a limit on N on my machine of about 6.71e+7 (2.22e-16 ~ 1/(6.71e+7)^2).

##<a name="14"></a> ℝ
For the purpose of this "paper", ℝ just needs to include the series I'm working with.
That is ℝ augments ℚ with Σuₙ as follows:

    ℚ{uₙ: |uₙ|≤1/n² ← n≥N}, v=Σuₙ ↔ ℝ{v}, ℚ{L[Σₙuₙ]}

So I just need ℝ to work with L[Σuₙ].
ℝ has well defined `+` and `*`:

    uᵒ=Σuₙ,vᵒ=Σvₙ → uᵒ+vᵒ ≡ Σ uₙ+vₙ, uᵒvᵒ ≡ ΣΣ uₙvₘ

ℝ can be scaled by a rational:

    ℚ{v,uₙ}, ℝ{uᵒ:uᵒ=Σuₙ} → vuᵒ = vΣuₙ = Σvuₙ, ℝ{vuᵒ}

Quick plausibility check:

    u=[1,2,3],v=[4,5,6] →
      uᵒ = Σuₙ = 1 + 2 + 3 = 6
      vᵒ = Σvₙ = 4 + 5 + 6 = 15
      # Addition
      uᵒ+vᵒ = Σ uₙ+vₙ = (1+4) + (2+5) + (3+6) = 5 + 7 + 9 = 21
      Σuₙ + Σvₙ = 6 + 15 = 21
      uᵒ+vᵒ = Σuₙ+Σvₙ = Σ uₙ+vₙ = 21   # All self consistent
      # Multiplication
      uᵒvᵒ = ΣΣ uₙvₘ = ((1*4)+(1*5)+(1*6)) + ((2*4)+(2*5)+(2*6)) + ((3*4)+(3*5)+(3*6))
        = (4+5+6) + (8+10+12) + (12+15+18)
        = 15 + 30 + 45
        = 90
      uᵒvᵒ = Σuₙ Σvₙ = 6*15 = 90
      uᵒvᵒ = Σuₙ Σvₙ = ΣΣ uₙvₘ = 90   # Again, consistent.
      # Division we don't have in the same form.
      uᵒ/vᵒ = Σuₙ/Σvₙ

    Σuₙ Σvₘ = ΣΣ uₙvₘ
    # The rigorous proof:
      Σuₙ Σvₘ
      (Σuₙ)*(Σvₘ)   # Just explicitly showing what I mean.
      Σ[uₙ*(Σvₘ)]   # Treat the v series like a number and take it into the u series.
      Σ[Σuₙvₘ)]     # uₙ is just a constant rational and can go into the v series.
      ΣΣ[uₙvₘ]      # Well... maybe it was obvious to begin with.

I'll be using ΣΣ[uₙvₘ]=Σ[uₙ]Σ[vₙ] later.

##<a name="15"></a> ℂ
Complex numbers:

    ℂ ≡ (ℝ,ℝ)
    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)+(vᵣ,vᵢ)≡(uᵣ+vᵣ,uᵢ+vᵢ)
      (uᵣ,uᵢ)(vᵣ,vᵢ)≡(u²ᵣ-v²ᵢ,uᵣvᵢ+uᵢvᵣ)
    ℂ{α,β}

##<a name="16"></a> i
The Imaginary number i:

    i ≡ (0,1)
    i² = (-1,0)
    # Proof
      (0,1)(0,1)
      (0²-1²,0*1+1*0)
      (-1,0)
    (u,v) = u+iv
    i² = -1

##<a name="17"></a> †
Complex conjugation:

    (u,v)†  ≡ (u,-v)                 # Think † means adjoin? Go to the beginning where I define ≡.
    (u+iv)† = u-iv
    e[i]† = (C+iS)† = C-iS = e[-i]   # what it does to e

##<a name="18"></a> &lt;u&gt;
Dirac notation:

    <αu|βu> ≡ ΣΣ (αuₙ)†(βuₘ)
    <αu|βu> = α†<u|βu> = β<αu|u>
    <αu|βu>† = <βv|αu>
    <αu| + <βv| = <αu+βv|

    <u> ≡ <u|u>

    <αu> = α†α<u>
    # Proof
      <αu>
      <αu|αu>
      α†<u|αu>
      α†α<u|u>
      α†α<u>

    |n> ≡ |uₙ>   # where u is know from context

    <u|l> = uₗ†uₗ
    # Proof
      <u|l>
      <u|uₗ>
      ΣΣ uₙ†uₗ
      uₗ†uₗ   # uₙ are orthogonal, only the l term contributes

    <uₗ> ≡ uₗ†uₗ
    <u|l> = <uₗ>
    <α> = α†α
    # TODO: What we mean by average value,  <u> ≡ Σₙuₙ/N ?

##<a name="19"></a> n!
Factorial:

    n! ≡ Π[1,n]{u|u}   # 1*2*3*...*n

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
      -1*0
      0   # In general 1/u! = 0 ← ℤ{u<0}

##<a name="20"></a> nᵥ
I'd like to make the following refinement in ℕ,
Whatchamacallit forward:

    nᵥ ≡ nᵥ-₁(n+v)
    n₀ ≡ 1

    n₁ = n₀(n+1)
    n₁ = n+1

    n₂ = n₁(n+2)
    n₂ = (n+1)(n+2)

    n₃ = n₂(n+3)
    n₃ = (n+1)(n+2)(n+3) # and so on...

    4₂ = (4+1)(4+2) = 5*6 = 30   # For example.

Whatchamacallit backwards:

    nᵥ-₁ = nᵥ/(n+v)
    nᵥ = nᵥ+₁/(n+v+1)

    n-₁ = n₀/(n-1+1) = 1/n
    n-₁ = 1/n

    n-₂ = n-₁/(n-2+1) = (1/n)/(n-1)
    n-₂ = 1/(n(n-1))

    n-₃ = n-₂/(n-3+1) = (1/(n(n-1)))/(n-2)
    n-₃ = 1/(n(n-1)(n-2)) # and so on...

    4-₂ = 1/(4(4-1)) = 1/(4*3) = 1/12   # For example.

Arrows meaningful as Whatchamacallits:

    n⇈ = (n+1)(n+2)
    n↑ = n+1
    n₀ = 1
    n↓ = 1/n
    n⇊ = 1/(n(n-1))

Whatchamacallit with Factorial:

    nᵥn! = (n+v)!

    n₃n! = (n+1)(n+2)(n+3)n! = (n+3)!   # OK

    n-₃n! = n!/(n(n+1)(n+2))
    n-₃n! = (n-3)!(n-2)(n-1)n/(n(n-1)(n-2))
    n-₃n! = (n-3)!   # OK

    n↑n! = (n+1)!
    n↓n! = (n-1)!

    n⇈n! = (n+2)!
    n⇊n! = (n-2)!

##<a name="21"></a> (ⁿₘ)
[Binomial coefficient](http://en.wikipedia.org/wiki/Binomial_coefficient),
n choose m:

    (ⁿₘ) ≡ n!/(m!(n-m)!)

    (ⁿₘ) = 1/(n-ₘm!)
    # Proof
      (ⁿₘ)
      n!/(m!(n-m)!)
      n!/(m!n!n-ₘ)
      1/(m!n-ₘ)

##<a name="22"></a> Sine, Cosine, and Exponential
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
    C[2u]=1-2S²u       # Cosine double angle "cos(2u)=1-2*sin²(u)"

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

##<a name="23"></a> Δ²
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

##<a name="24"></a> Pₙ
P is the [Poisson distribution](http://en.wikipedia.org/wiki/Poisson_distribution):

    Pₙ ≡ uⁿe[-u]/n!
    Σ Pₙ = 1
    0 ≤ Pₙ ≤ 1
    <u> = Σ Pₙuₙ

##<a name="25"></a> pₙ

    pₙ ≡ √[uⁿe[-u]/n!]
    pₙ†pₙ = Pₙ
    # Proof
      pₙ†pₙ
      √[uⁿe[-u]/n!]†√[uⁿe[-u]/n!]
      √[uⁿe[-u]/n!]√[uⁿe[-u]/n!]   # It's just all real.
      uⁿe[-u]/n!
      Pₙ

##<a name="26"></a> Fundamental values
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

##<a name="27"></a> Derived values

    ω² ≡ k/m   # Angular frequency
    ω = √[k/m]

    f ≡ ω/(2π)   # Frequency

TODO: need to explain ħ.

    Eₙ = ωħ(n+½)   # 3.2: Energy eigen-value

##<a name="28"></a> Φᵗₙ
7.17 TODO: why -iEₙt/ħ and not +iEₙt/ħ?
Time evolution:

    Φᵗₙ ≡ e[-iω(n+½)t] = e[-iEₙt/ħ]   # NOTE! The ½ part makes this object a bit of a screw ball.
    φᵗₙ ≡ e[-iωnt]                    # "How do we end up with this?" you may ask.

    Φₙ†Φₘ = φₘ-ₙ   # You don't have to explicitly show time if it can be infered.
    # Proof:
      Φₙ†Φₘ
      Φ-ₙΦₘ
      e[iω(n+½)t - iω(m+½)t]
      e[-iω(m-n)t]
      φₘ-ₙ

    # Don't have to explicitly show quantum number if it can be infered.
    Φ⁰ = 1
    Φⁱ = e[-iω(n+½)]
    Φᵗ = (Φⁱ)^t = e[t * (-iω(n+½))] = e[-iω(n+½)t]   # Just to show that the notation makes sense.

##<a name="29"></a> Φ→φ

    Φₙ†Φₙ+₁ = φₙ+₁-ₙ = φ₁
    φ↥ ≡ φ₀↑ = φ₁   # This will make notation very consistent later.
    Φₙ†Φₙ+₁ = φ↥

    Φₙ†Φₙ-₁ = φₙ-₁-ₙ = φ-₁   # Yeah... me worry about this one a little bit!  LOL
    φ↧ ≡ φ₀↓ = φ-₁
    Φₙ†Φₙ-₁ = φ↧

    Φₙ†Φₙ+₂ = φₙ+₂-ₙ = φ₂
    Φₙ†Φₙ-₂ = φₙ-₂-ₙ = φ-₂

# sₙ, cₙ
Short for Sine(nωt) and Cosine(nωt):

    sₙ ≡ S[nωt]
    cₙ ≡ C[nωt]
    c₂ₙ=1-2s²ₙ   # Cosine double angle in terms of c and s.

    φₙ = cₙ-isₙ   # φ in terms of c and s.

    φ₁ = c₁-is₁

    φ-₁ = c₁+is₁   # Maybe that'll work.

    φ₁ + φ-₁ = 2c₁
    φ↥ + φ↧ = 2c₁   # Remember this one!

    φ₁ - φ-₁ = 2s₁
    φ↥ - φ↧ = 2s₁

    φ₂ = c₂-is₂
    φ-₂ = c₂+is₂

    φ-₂ + φ₂ = 2c₂
    φ↧↓ + φ↥↑ = 2c₂   # And remember this one!

##<a name="30"></a> nᵒ
Average Quantum number nᵒ

    <n> = <n|pₙ†npₙ|m> = Σ npₙpₙ = Σ nPₙ   # only n=m terms contribute

    nᵒ ≡ L <n>
    nᵒ = L Σ nPₙ = L Σₙ nPₙ   # Remember that L truncates the series.

    Σₙ nPₙ = L Σₙ nuⁿe[-u]/n!                    # Just by definition of Pₙ.
     = Σ[0,M]{n|nuⁿe[-u]/n!}                     # Definition of Σₙ.
     = 0 + Σ[1,M]{n|nuⁿe[-u]/n!}                 # The first element in the series is just zero.
     = Σ[1,M]{n|uⁿe[-u]/(n-1)!}                  # Have the n factor absorbed by the factorial.
     = Σ[0,M-1]{n|u[n+1]e[-u]/n!}                # Shift.
     = uΣ[0,M-1]{n|uⁿe[-u]/n!}                   # Take out a factor of u.
     = u(Σ[0,M]{n|uⁿe[-u]/n!} - (u^M)e[-M]/M!)   # Add and subtract the an Nth element (which is M).
     = u(ΣₙPₙ) - u(u^M)e[-M]/M!                  # Definition of Σₙ and Pₙ.
     = u(1) - u^(M+1)e[-M]/M!                    # Poisson distribution sums up to one.
     = u - u^(M+1)e[-M]/M!

    nᵒ = L[u - u^(M+1)e[-M]/M!]
    nᵒ = L[u] - L[u^(M+1)e[-M]/M!]
    nᵒ = u - 0
    nᵒ = u   # As expected.  :)

##<a name="31"></a> L Σ[n(n-1)Pₙ]

    L Σ n(n-1)Pₙ
    L Σₙ n(n-1)Pₙ
    L Σₙ 1/n-₂ uⁿe[-u]/n!
    L Σₙ uⁿe[-u]/(n-2)!
    L Σₙ u² u^(n-2)e[-u]/(n-2)!
    L u² Σₙ u^(n-2)e[-u]/(n-2)!
    L u² Σ[0,M]{n|u^(n-2)e[-u]/(n-2)!}
    L u² Σ[-2,M-2]{n|uⁿe[-u]/n!}
    L u² (Σ[-2,-1]{n|uⁿe[-u]/n!} + Σ[0,M-2]{n|uⁿe[-u]/n!})
    L u² (Σ[-2,-1]{n|uⁿe[-u]/n!} + Σ[0,M-2]{n|Pₙ})
    u²(L[e[-u]/(u²(-2)!)] + L[e[-u]/(u(-1)!)] + L[Σ[0,M-2]{n|Pₙ}])
    u²(0 + 0 + L[Σ[0,M-2]{n|Pₙ}])   # 1/u! = 0 if integer u < 0
    u²(L[Σ[0,M]{n|Pₙ} - P[M-1] - P[M]])
    u²(L[ΣPₙ - P[M-1] - P[M]] - P[M+1] - ⋯)   # Re-consider the infinite series.
    u²(L[1 - P[M-1] - P[M]] - P[M+1] - ⋯)     # ΣPₙ = 1
    u²(1 - L[P[M-1] - P[M]] - P[M+1] - ⋯])
    # To L, for large enough M, the trailing sequence are all zeroes.
    u²(1 - Σ0)
    u²(1-0)
    u²*1
    u²

    nᵒ² = L Σ[n(n-1)Pₙ]   # b/c nᵒ=u, so u²=nᵒ²

Now we can describe the distribution in terms of the average quantum number:

    Pₙ = nᵒⁿe[-nᵒ]/n!
    pₙ = √[nᵒⁿe[-nᵒ]/n!]

##<a name="32"></a> p→P

    pₙpₙ+₁ = √[nᵒⁿe[-nᵒ]/n!] √[nᵒ^(n+1)e[-nᵒ]/(n+1)!]
           = √[nᵒⁿe[-nᵒ]/n!] √[nᵒⁿe[-nᵒ]/n!] √[nᵒ/(n+1)] 
           = pₙ pₙ √[nᵒ/(n+1)] 
           = Pₙ √[nᵒ/(n+1)] 
           = √[nᵒ/(n+1)]Pₙ 
    pₙpₙ+₁ = √nᵒPₙ/√n₁   # Using Whatchamacallit
    pp↑ = √nᵒPₙ/√n↑      # And Arrow notation

    pₙpₙ-₁ = √[nᵒⁿe[-nᵒ]/n!] √[nᵒ^(n-1)e[-nᵒ]/(n-1)!]
           = √[nᵒⁿe[-nᵒ]/n!] √[nᵒⁿe[-nᵒ]/n!] √[n/nᵒ] 
           = pₙ pₙ √[n/nᵒ] 
           = Pₙ √[n/nᵒ] 
           = √[n/nᵒ]Pₙ 
    pₙpₙ-₁ = Pₙ/√[nᵒn-₁]   # Using Whatchamacallit
    pp↓ = Pₙ/√[nᵒn↓]       # And Arrow notation

    pₙpₙ+₂ = √[nᵒⁿe[-nᵒ]/n!] √[nᵒ^(n+2)e[-nᵒ]/(n+2)!]
           = √[nᵒ²/((n+1)(n+2))] √[nᵒⁿe[-nᵒ]/n!] √[nᵒⁿe[-nᵒ]/n!]
           = nᵒ/√[(n+1)(n+2)] pₙpₙ
           = nᵒ/√[(n+1)(n+2)] Pₙ
    pₙpₙ+₂ = nᵒPₙ/√n₂   # Using Whatchamacallit
    pₙpₙ+₂ = nᵒPₙ/√n⇈   # Using Arrow

    pₙpₙ-₂ = √[nᵒⁿe[-nᵒ]/n!] √[nᵒ^(n-2)e[-nᵒ]/(n-2)!]
           = √[(n-1)n/nᵒ²] √[nᵒⁿe[-nᵒ]/n!] √[nᵒⁿe[-nᵒ]/n!]
           = √[(n-1)n]/nᵒ pₙpₙ
           = √[(n-1)n]/nᵒ Pₙ
    pₙpₙ-₂ = Pₙ/(nᵒ√n-₂)   # Using Whatchamacallit
    pₙpₙ-₂ = Pₙ/(nᵒ√n⇊)    # Using Arrow

    p = √m↑p↑/√nᵒ
    # Proof:
      pp↑ = √nᵒP/√m↑
      p↑ = √nᵒp/√m↑
      √m↑p↑/√nᵒ = p
      p = √m↑p↑/√nᵒ

    p = √[nᵒm↓]p↓  
    # Proof:
      pp↓ = P/√[nᵒm↓]
      p↓ = p/√[nᵒm↓]
      √[nᵒm↓]p↓ = p
      p = √[nᵒm↓]p↓

##<a name="33"></a> ξ
The non-dimensional displacement, ξ.

    ξ² ≡ mω/ħ x²   # A.1b
    x² = ħ/(mω) ξ²

##<a name="34"></a> Aₙ
The Normalization Constant, Aₙ:

    Aₙ ≡ 1/√[2ⁿn!√π]
    Aₙ/Aₙ-₁ = 1/√[2n]
    Proof:
      (1/√[2ⁿn!√π]) / (1/√[2ⁿ-ⁱ(n-1)!√π])
      (1/√[2ⁿn!√π]) * (√[2ⁿ-ⁱ(n-1)!√π])
      √[2ⁿ-ⁱ(n-1)!√π] / √[2ⁿn!√π]
      √[2ⁿ-ⁱ(n-1)!] / √[2ⁿn!]   # √π cancels
      √[2ⁿ-ⁱ] / √[2ⁿn]          # n!/(n-1)! = n
      1 / √[2n]                 # 2ⁿ/2ⁿ-ⁱ = 2

    # Identities:
    Aₙ   = Aₙ-₁ / √[2n]       # Given
    Aₙ+₁ = Aₙ   / √[2(n+1)]   # Increment index n
    Aₙ   = Aₙ+₁ * √[2(n+1)]   # Solve for Aₙ
    Aₙ-₁ = Aₙ   * √[2n]       # Decrement index n

    # With Whatchamacallits
    Aₙ   = Aₙ-₁ * √[½n-₁] = Aₙ-₁ * √[½n↓] = Aₙ-₁ * √[½n↓]
    Aₙ+₁ = Aₙ   / √[2n₁]  = Aₙ   / √[2n↑] = Aₙ   / √[2n↑]
    Aₙ   = Aₙ+₁ * √[2n₁]  = Aₙ+₁ * √[2n↑] = Aₙ+₁ * √[2n↑]
    Aₙ-₁ = Aₙ   / √[½n-₁] = Aₙ   / √[½n↓] = Aₙ   / √[½n↓]

    # Use these:
    Aₘ = √[2m↑]Aₘ↑ = √[½m↓]Aₘ↓

##<a name="35"></a> ℋₙ
The Hermite polynomial:

    ℋₙ[ξ] ≡ (-1)ⁿ e[ξ²] Dᵧⁿ e[-ξ²]   # A.3, this is "physicists' Hermite polynomials" in Wikipedia.

    Dᵧ ℋₙ[ξ] = 2nℋₙ-₁[ξ]   # A.4a
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
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²]((ⁿ₀) D⁰[-2ξ] Dⁿ-⁰e[-ξ²] + (ⁿ₁) Dⁱ[-2ξ] Dⁿ-ⁱe[-ξ²])
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²](   1 D⁰[-2ξ] Dⁿ  e[-ξ²] +    n Dⁱ[-2ξ] Dⁿ-ⁱe[-ξ²])
      (-1)ⁿ (2ξe[ξ²] Dⁿ e[-ξ²] + e[ξ²](         -2ξ  Dⁿ  e[-ξ²] +     n   (-2)  Dⁿ-ⁱe[-ξ²])
      (-1)ⁿ (2ξe[ξ²]Dⁿe[-ξ²] - 2ξe[ξ²]Dⁿe[-ξ²] - 2ne[ξ²]Dⁿ-ⁱe[-ξ²])
      (-1)ⁿ (0 - 2ne[ξ²]Dⁿ-ⁱe[-ξ²])
      (-1)ⁿ (-2) ne[ξ²]Dⁿ-ⁱe[-ξ²]
      (-1)ⁿ-ⁱ 2 ne[ξ²]Dⁿ-ⁱe[-ξ²]
      2n (-1)ⁿ-ⁱ e[ξ²] Dⁿ-ⁱe[-ξ²]
      2n ℋₙ-₁[ξ]

    ℋₙ+₁[ξ] = 2ξℋₙ[ξ] - 2nℋₙ-₁[ξ]   # A.4b
    # Also a well known property of ℋ, but here's a proof:
      ℋₙ+₁[ξ]
      (-1)ⁿ+ⁱ e[ξ²] Dⁿ+ⁱ e[-ξ²]
      (-1)ⁿ(-1) e[ξ²] Dⁿ[D e[-ξ²]]
      (-1)ⁿ(-1) e[ξ²] Dⁿ[(-2ξ) e[-ξ²]]
      (-1)ⁿ     e[ξ²] Dⁿ[  2ξ  e[-ξ²]]
      (-1)ⁿ e[ξ²] Σₘ (ⁿₘ) Dᵐ[2ξ] Dⁿ-ᵐ[e[-ξ²]]                                  # General Leibniz rule
      (-1)ⁿ e[ξ²]((ⁿ₀) D⁰[2ξ] Dⁿ-⁰[e[-ξ²]] + (ⁿ₁) Dⁱ[2ξ] Dⁿ-ⁱ[e[-ξ²]] + 0 ⋯)   # Dejavu
      (-1)ⁿ e[ξ²](   1   (2ξ) Dⁿ  [e[-ξ²]] +    n   (2)  Dⁿ-ⁱ[e[-ξ²]])
      (-1)ⁿ e[ξ²](2ξDⁿ[e[-ξ²]] + 2nDⁿ-ⁱ[e[-ξ²]])
      (-1)ⁿ e[ξ²] 2ξDⁿ[e[-ξ²]] + (-1)ⁿ e[ξ²] 2nDⁿ-ⁱ[e[-ξ²]])                   # Distribute
      2ξ (-1)ⁿ e[ξ²] Dⁿ[e[-ξ²]] + 2n (-1)ⁿ e[ξ²] Dⁿ-ⁱ[e[-ξ²]])
      2ξ (-1)ⁿ e[ξ²] Dⁿ[e[-ξ²]] + 2n (-1)(-1)ⁿ-ⁱ e[ξ²] Dⁿ-ⁱ[e[-ξ²]])
      2ξ (-1)ⁿ e[ξ²] Dⁿ[e[-ξ²]] - 2n (-1)ⁿ-ⁱ e[ξ²] Dⁿ-ⁱ[e[-ξ²]])
      2ξℋₙ[ξ] - 2nℋₙ-₁[ξ]

    ξℋₙ[ξ] = ½ℋₙ+₁[ξ] + nℋₙ-₁[ξ]
    # Proof
      ℋₙ+₁[ξ] = 2ξℋₙ[ξ] - 2nℋₙ-₁[ξ]
      ℋₙ+₁[ξ] + 2nℋₙ-₁[ξ] = 2ξℋₙ[ξ]
      2ξℋₙ[ξ] = ℋₙ+₁[ξ] + 2nℋₙ-₁[ξ]
      ξℋₙ[ξ] = ½ℋₙ+₁[ξ] + nℋₙ-₁[ξ]


    # Can also be written as:
    Dᵧ ℋₙ[ξ] = 2nℋₙ-₁[ξ]           = ℋₙ↓[ξ]/(½n↓)
    ξℋₙ[ξ]   = ½ℋₙ+₁[ξ] + nℋₙ-₁[ξ] = ½(ℋₙ↑[ξ] + ℋₙ↓[ξ]/(½n↓))

##<a name="36"></a> Ψₙ
Please accept the EigenState of the Simple Harmonic Oscillator Ψₙ as given by Liboff's book in page 189.
The EigenState Ψₙ:

    Ψₙ[x] ≡ |n>
    Ψₙ[x] = Aₙℋₙ[ξ]e[-ξ²/2]

The State Function Ψ:

    Ψ[x] = Σ pₙ Ψₙ[x]   # TODO: or is it Σ Pₙ Ψₙ[x] ? Check Σ pₙ = 1 ?

The Problem To Be Solved

    Minimize:     <Ψ|n><n|ΔxΔp|m><m|Ψ>
    Subject to:   <Ψ|n><n|Eₙ|n><n|Ψ> = Eᵒ

TODO: I just jumped from the above to the calculation of Δ²x !?
Will say something like ΣΣuₙvₘ = (Σuₙ)(Σvₙ)

##<a name="37"></a> ξΨₘ
Motivation: I will be calculating <Ψ|ξ|Ψ> later.

    ξΨₘ = ½Aₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
    # Proof:
      ξΨₘ
      ξAₘℋₘ[ξ]e[-ξ²/2]
      Aₘ ξℋₘ[ξ]e[-ξ²/2]
      Aₘ ½(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
      ½Aₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))

##<a name="38"></a> &lt;ξ₀&gt;
Evaluation of `<ξ₀>`:

    <ξ₀> = <Ψ₀|ξ|Ψ₀>             # 7.14a
    <ξ₀> = <Ψ₀|n><n|ξ|m><m|Ψ₀>   # 7.14b

    <ξ₀> = ΣΣ (pₙΨₙ)† ξ (pₘΨₘ)
    <ξ₀> = ΣΣ Ψₙ†pₙ pₘξΨₘ                                          # rearrange, p is real.
    <ξ₀> = ΣΣ Ψₙ†pₙ pₘ ½Aₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))                  # substitute for ξΨₘ
    <ξ₀> = ΣΣ Ψₙ†pₙ ½Aₘ(pₘℋₘ↑[ξ] + pₘℋₘ↓[ξ]/(½m↓))                 # distribute pₘ
    <ξ₀> = ΣΣ[pₙΨₙ†pₙ ½Aₘpₘℋₘ↑[ξ]] + ΣΣ[Ψₙ†pₙ ½Aₘpₘℋₘ↓[ξ]/(½m↓)]   # separate
    <ξ₀> = ½ΣΣ[Ψₙ†pₙ pₘ Aₘℋₘ↑[ξ]] + ½ΣΣ[Ψₙ†pₙ pₘ Aₘℋₘ↓[ξ]/(½m↓)]   # take out ½
    # get the m's to match
    <ξ₀> = ½ΣΣ[Ψₙ†pₙ √m↑pₘ↑/√nᵒ √[2m↑]Aₘ↑ℋₘ↑[ξ]] + ½ΣΣ[Ψₙ†pₙ √[nᵒm↓]pₘ↓ √[½m↓]Aₘ↓ℋₘ↓[ξ]/(½m↓)]
    <ξ₀> = 1/√[2nᵒ]ΣΣ[Ψₙ†pₙ m↑pₘ↑Aₘ↑ℋₘ↑[ξ]] + √[½nᵒ]ΣΣ[Ψₙ†pₙ pₘ↓Aₘ↓ℋₘ↓[ξ]]
    <ξ₀> = 1/√[2nᵒ]ΣΣ[Ψₙ†pₙ m↑ pₘ↑Ψₘ↑] + √[½nᵒ]ΣΣ[Ψₙ†pₙ pₘ↓Ψₘ↓]
    <ξ₀> = 1/√[2nᵒ]Σ[Ψₙ†pₙ n pₙΨₙ] + √[½nᵒ]Σ[Ψₙ†pₙpₙΨₙ]           # Orthogonal states
    <ξ₀> = 1/√[2nᵒ]ΣΣ[nPₙ] + √[½nᵒ]Σ[Pₙ]                          # Ψₙ†Ψₙ=1, pₙpₙ=Pₙ
    <ξ₀> = 1/√[2nᵒ]nᵒ + √[½nᵒ]
    <ξ₀> = √[½nᵒ] + √[½nᵒ]
    <ξ₀> = 2√[½nᵒ]
    <ξ₀> = √[2nᵒ]
    <ξ₀>² = 2nᵒ   # OK, need time development

##<a name="39"></a> ΦAℋ↓/½n↓=Φ↥/√½n↓Φ↓Ψ↓

    ΦAℋ↓/½n↓
    Φ√[½n↓]A↓ℋ↓/½n↓   # A=√[½n↓]A↓
    ΦA↓ℋ↓/√[½n↓]
    Φ↥Φ↓A↓ℋ↓/√½n↓     # Φ=Φ₁Φ↓
    Φ↥/√½n↓ Φ↓A↓ℋ↓
    Φ↥/√½n↓ Φ↓Ψ↓

##<a name="40"></a> ΦAℋ↑=Φ↧√2n↑Φ↑Ψ↑

    ΦAℋ↑
    Φ√2n↑A↑ℋ↑   # A=√[2n↑]A↑
    Φ↧Φ↑√2n↑A↑ℋ↑
    Φ↧Φ↑√2n↑A↑ℋ↑
    Φ↧√2n↑ Φ↑A↑ℋ↑
    Φ↧√2n↑ Φ↑Ψ↑

##<a name="41"></a> p↑p=√[nᵒ/n↑]P

    p↑p
    √[nᵒⁿ+ⁱe[-nᵒ]/(n+1)!] p
    √[nᵒ/(n+1) nᵒⁿe[-nᵒ]/n!] p
    √[nᵒ/(n+1)]p p
    √[nᵒ/(n+1)]P
    √[nᵒ/n₁]P
    √[nᵒ/n↑]P

##<a name="42"></a> p↓p=P/√[n↓nᵒ]

   p↓p
    √[nᵒⁿ-ⁱe[-nᵒ]/(n-1)!] p
    √[(n/nᵒ) nᵒe[-nᵒ]/n!] p
    √[n/nᵒ] p p
    √[1/(n-₁nᵒ)]P
    P/√[n-₁nᵒ]
    P/√[n↓nᵒ]

##<a name="43"></a> &lt;ξₜ&gt;
Evaluation of `<ξₜ>`:

    <ξₜ> = <Ψ|ξ|Ψ>
    <ξₜ> = <Ψ|n><n|ξ|m><m|Ψ>
    <ξₜ> = ΣΣ (pₙΦᵗₙΨₙ)† ξ (pₘΦᵗₘΨₘ)
    # Parralles <ξ₀> up to the here...
    <ξₜ> = ½ΣΣ[(ΦᵗₙΨₙ)†pₙ pₘ ΦᵗₘAₘℋₘ↑[ξ]] + ½ΣΣ[ΦᵗₙΨₙ†pₙ pₘ ΦᵗₘAₘℋₘ↓[ξ]/(½m↓)]
    <ξₜ> = ½(Σ[(ΦΨ)†p]Σ[pΦAℋ↑[ξ]] + Σ[(ΦΨ)†p]Σ[pΦAℋ↓[ξ]/½n↓])            # ΣΣ[αₙβₘ]=Σ[αₙ]Σ[βₙ], context indeces.
    <ξₜ> = ½(Σ[(Φ↑Ψ↑)†p↑]Σ[pΦ↧√2n↑Φ↑Ψ↑] + Σ[(Φ↓Ψ↓)†p↓]Σ[pΦ↥/√½n↓Φ↓Ψ↓])   # TODO: What am I doing here???
    <ξₜ> = ½(Σ[(Φ↑Ψ↑)†p↑pΦ↧√2n↑Φ↑Ψ↑] + Σ[(Φ↓Ψ↓)†p↓pΦ↥/√½n↓Φ↓Ψ↓])         # Orthogonal states
    <ξₜ> = ½(Σ[p↑pΦ↧√2n↑] + Σ[p↓pΦ↥/√½n↓])                               # Normalized states, Ψ†Ψ=1
    <ξₜ> = ½(Σ[√[nᵒ/n↑]PΦ↧√2n↑] + Σ[PΦ↥/√[n↓nᵒ]/√½n↓])
    <ξₜ> = ½(Σ[√nᵒPΦ↧√2] + Σ[PΦ↥/√½nᵒ/n↓])
    <ξₜ> = ½(Σ[√nᵒPΦ↧√2] + Σ[PnΦ↥/√½nᵒ])
    <ξₜ> = ½(Σ[√2nᵒPΦ↧] + Σ[PnΦ↥/√½nᵒ])
    <ξₜ> = ½(√2nᵒΦ↧Σ[P] + Φ↥/√½nᵒΣ[Pn])
    <ξₜ> = ½(√2nᵒΦ↧Σ[P] + Φ↥√[2nᵒ])
    <ξₜ> = ½(√2nᵒΦ↧ + Φ↥√[2nᵒ])
    <ξₜ> = ½√2nᵒ(Φ↧ + Φ↥)
    <ξₜ> = ½√2nᵒ(2c₁)
    <ξₜ> = √2nᵒ c₁
    <ξₜ>² = 2nᵒ c₁
    <ξₜ>² = 2nᵒ:Cosine²[nwt]
    # This time I got Cosine... Why?  Not careful enough with φ↥ and φ↧?

##<a name="44"></a> &lt;ξ²&gt;
TODO: `<ξ²>`:

    # And who wants to work with this mess?
    <ξ²> = (nᵒ+½) +
      ½Σ e[-iω(n+½)t]† √[uⁿe[-u]/n!] (
        e[-iω((n-2)+½)t] √[n(n-1)] √[u^(n-2)e[-u]/(n-2)! +
        e[-iω((n+2)+½)t] √[(n+1)(n+2)] √[u^(n+2)e[-u]/(n+2)!
      )
    <ξ²> = (nᵒ+½) + ½Σ Φₙ†pₙ† (Φₙ-₂√[n(n-1)]pₙ-₂ +  Φₙ+₂√[(n+1)(n+2)]pₙ+₂)   # 7.21
    # And much nicer...
    <ξ²> = (nᵒ+½) + ½Σ Φ†p (Φ⇊/√n⇊ p⇊ +  Φ⇈√n⇈ p⇈)                           # pretty noted
    <ξ²> = (nᵒ+½) + ½Σ Φ†Φ⇊/√n⇊ pp⇊ +  Φ†Φ⇈√n⇈ pp⇈                           # Distribute
    <ξ²> = (nᵒ+½) + ½Σ φ↧↓/√n⇊ pp⇊ +  φ↥↑√n⇈ pp⇈                             # Φ→φ
    <ξ²> = (nᵒ+½) + ½Σ φ↧↓/√n⇊ P/(nᵒ√n⇊) +  φ↥↑√n⇈ nᵒP/√n⇈                   # p->P
    <ξ²> = (nᵒ+½) + ½Σ φ↧↓/n⇊ P/nᵒ +  φ↥↑ nᵒP                                # Simplify
    <ξ²> = (nᵒ+½) + ½Σ φ↧↓ n(n-1) P/nᵒ +  φ↥↑ nᵒP                            # 1/n⇊ = n(n-1)
    <ξ²> = (nᵒ+½) + ½(Σ[φ↧↓ n(n-1) P/nᵒ] +  Σ[φ↥↑ nᵒP])                      # Separate sums
    <ξ²> = (nᵒ+½) + ½(φ↧↓/nᵒΣ[n(n-1)P] +  φ↥↑nᵒΣ[P])                         # Take out the constants
    <ξ²> = (nᵒ+½) + ½(φ↧↓/nᵒ(nᵒ²) +  φ↥↑nᵒ(1))                               # Evaluate sums
    <ξ²> = (nᵒ+½) + ½(φ↧↓nᵒ + φ↥↑nᵒ)                                         # Simplify
    <ξ²> = (nᵒ+½) + ½nᵒ(φ↧↓ + φ↥↑)
    <ξ²> = (nᵒ+½) + ½nᵒ(2c₂)                                                 # Remember?  φ↧↓+φ↥↑=2c₂.
    <ξ²> = (nᵒ+½) + nᵒc₂
    <ξ²> = (nᵒ+½) + nᵒ(1-2s²₁)                                               # Double angle, c₂=1-2s²₁
    <ξ²> = (nᵒ+½) + nᵒ- 2nᵒs²₁
    <ξ²> = 2nᵒ + ½ - 2nᵒs²₁
    <ξ²> = ½ + 2nᵒ - 2nᵒs²₁
    <ξ²> = ½ + 2nᵒ(1 - s²₁)
    <ξ²> = ½ + 2nᵒc²₁                                                        # Pythagoras
    <ξ²> = ½ + 2nᵒ:Cosine²[nwt]

##<a name="45"></a> Results
7.5 Results:

    Δ²ξ = <ξ²> - <ξ>²
        = (½ + 2nᵒc²₁) - 2nᵒc²₁
        = ½
