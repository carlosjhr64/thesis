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

## {u,v}
Arbitrary symbols:

     {u}         # I conjure up u of any type.
     v≡u → v=u   # If I define v as u, then v is u, capiche?
     u≡u         # So I tell you things are themselves.
     u=u         # Then you accept things are themselves.

## Precedence rules

    uuu ≡ ((uu)u)     # This is just the usual way we think of expressions.
    u u u ≡ (u(uu))   # This is to disambiguate things like "Σ ab" which means "Σ[ab]", not "Σ[a]b".
    # Modifiers like subscripts, superscripts, factorial, complex conjugate, arrow operators.
    u!u ≡ (u!)u

## ℕ
Natural (Counting) numbers:

    ℕ ≡ {0,1,2,3,⋯}   # The set of Natural numbers.  Or the ordered type /^\d+$/.
    ℕ{N,n,m}          # N, M, n, and m are Natural numbers.
    M≡N-1             # This just simplifies notation later on.

## ℤ and ℚ
See njwildberger's [MathFoundations](https://www.youtube.com/user/njwildberger).
Integers and Rationals:

    ℤ ≡ ℕ - ℕ          # u-v, like 1-2 or just "-1".
    ℚ ≡ ℤ / ℕ{n:n≠0}   # u/v, like ½ or just "0.5".
    ℤ{l}               # l is an Integer.

## uᵥ
Subcripts labels a specific form of a more general expression:

    uᵥ[⋯]≡u[v,⋯]
    uₙₘ≡u[n,m,⋯]

## Π

    # 1.upto(m).inject(1){|v,n|v*u[n]}
    Π[1,0] ≡ 1
    Π[1,m]{n|uₙ} ≡ u₁*u₂*⋯*uₙ-₁*uₙ*uₙ+₁*⋯*uₘ-₁*uₘ
    Π[1,2]{u} = u*u
    Π[1,3]{n|n} = 1*2*3

## uᵛ
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

## √u
Squareroot:

    √[u²]≡u
    √[uu]=u

## |u|
Absolute value:

    ℚ{u},|u|≡(u>0)?u:-u

## Σ
Summation over indeces:

    Σuₙ ≡ u₀ + u₁ + u₂ + ⋯   # Non-halting series.
    ΣΣuₙₘ ≡ (u₀₀ + u₀₁ + u₀₂ + ⋯) + (u₁₀ + u₁₁ + u₀₂ + ⋯) + (u₂₀ + u₂₁ + u₂₂ + ⋯) + ⋯

    Σₙuₙ ≡ Σ[0,M]{n|u[n]}   # NOTE!  Series indeces start with zero.
    ΣₙΣₘuₙₘ ≡ Σ[0,M]{n| Σ[0,M]{m| u[n,m]}}

    N = Σₙ 1

## Arrow operators
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

## Limit function
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

## ℝ
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

## ℂ
Complex numbers:

    ℂ ≡ (ℝ,ℝ)
    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)+(vᵣ,vᵢ)≡(uᵣ+vᵣ,uᵢ+vᵢ)
      (uᵣ,uᵢ)(vᵣ,vᵢ)≡(u²ᵣ-v²ᵢ,uᵣvᵢ+uᵢvᵣ)
    ℂ{α,β}

## i
The Imaginary number i:

    i ≡ (0,1)
    i² = (-1,0)
    # Proof
      (0,1)(0,1)
      (0²-1²,0*1+1*0)
      (-1,0)
    (u,v) = u+iv
    i² = -1

## †
Complex conjugation:

    (u,v)†  ≡ (u,-v)                 # Think † means adjoin? Go to the beginning where I define ≡.
    (u+iv)† = u-iv
    e[i]† = (C+iS)† = C-iS = e[-i]   # what it does to e

## &lt;u&gt;
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

## n!
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
      0	# In general 1/u! = 0 ← ℤ{u<0}

## nᵥ
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

## (ⁿₘ)
[Binomial coefficient](http://en.wikipedia.org/wiki/Binomial_coefficient),
n choose m:

    (ⁿₘ) ≡ n!/(m!(n-m)!)

    (ⁿₘ) = 1/(n-ₘm!)
    # Proof
      (ⁿₘ)
      n!/(m!(n-m)!)
      n!/(m!n!n-ₘ)
      1/(m!n-ₘ)

## Sine, Cosine, and Exponential
[Trigonometric](http://en.wikipedia.org/wiki/Trigonometric_functions#Series_definitions) and
[Exponential](http://en.wikipedia.org/wiki/Exponential_function#Formal_definition)
functions series definitions:

    :Sine[u] ≡ Σ (-1)ⁿ u^(2n+1) / (2n+1)!
    S[u] ≡ :Sine[u]

    :Cosine[u] ≡ Σ (-1)ⁿ u^(2n) / (2n)!
    C[u] ≡ :Cosine[u]

    :Exponential[u] ≡ Σ uⁿ / n!
    e[u] ≡ :Exponential[u]
    eᵘ ≡ e^(u) ≡ e[u]	# Alternate forms.

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

## Δ²
Measure of uncertainty defined (4.1a):

    Δ²[u] ≡ <(u - <u>)²>
    Δ²u ≡ <(u - <u>)²> 	# Allow the shorter form if unambiguous.

    Δ[u] ≡ √[Δ²u]	# I only defined Δ² and a not in terms of Δ, so...
    Δu ≡ √[Δ²u]	# Again, allow the shorter form.

    # Deriving 4.1b:
    Δ²u = <u² - 2u<u> + <u>²>
    Δ²u = <u²> - 2<u><u> + <u>²
    Δ²u = <u²> - 2<u>² + <u>²
    Δ²u = <u²> - <u>²

Measure of uncertainty (4.1b):

    Δ²u = <u²> - <u>²

## Pₙ
P is the [Poisson distribution](http://en.wikipedia.org/wiki/Poisson_distribution):

    Pₙ ≡ uⁿe[-u]/n!
    Σ Pₙ = 1
    0 ≤ Pₙ ≤ 1
    <u> = Σ Pₙuₙ

## pₙ

    pₙ ≡ √[uⁿe[-u]/n!]
    pₙ†pₙ = Pₙ
    # Proof
      pₙ†pₙ
      √[uⁿe[-u]/n!]†√[uⁿe[-u]/n!]
      √[uⁿe[-u]/n!]√[uⁿe[-u]/n!]   # It's just all real.
      uⁿe[-u]/n!
      Pₙ

## Fundamental values
I think the point here is that these values are "measured" by "experiment" in "some way".

    ℝ{m}	# Mass
    ℝ{k}	# Spring contant 

What about π ?
You can check that there exist several series 
of rational terms that produce [π](http://en.wikipedia.org/wiki/Pi):

    ℝ{π} ← π = 4 Σ (-1)ⁿ/(2n+1) # http://en.wikipedia.org/wiki/Leibniz_formula_for_π
    # Proof:
      π
      4 Σ (-1)ⁿ/(2n+1)
      4 Σ 1/(2(2n)+1) - 1/(2(2n+1)+1)	# pairing the alternating series
      4 Σ 1/(4n+1) - 1/(4n+3)
      4 Σ ((4n+3)-(4n+1))/((4n+1)(4n+3))
      4 Σ 2/((4n+1)(4n+3))
      Σ 8/((4n+1)(4n+3))
        |8/((4n+1)(4n+3))| ≤ |8/(16n²)| ≤ |1/(2n²)| ≤ 1/n² ← n≥N	# Fits given definition of ℝ.

## Derived values

    ω² ≡ k/m	# Angular frequency
    ω = √[k/m]

    f ≡ ω/(2π)	# Frequency

TODO: need to explain ħ.

    Eₙ = ωħ(n+½)	# 3.2: Energy eigen-value

## Φₙ
7.17 TODO: why -iEₙt/ħ and not +iEₙt/ħ?
Time evolution:

    Φᵗₙ ≡ e[-iω(n+½)t] = e[-iEₙt/ħ]	# NOTE! The ½ part makes this object a bit of a screw ball.
    φᵗₙ ≡ e[-iωnt]	# "How do we end up with this?" you may ask.

    Φₙ†Φₘ = φₘ-ₙ	# You don't have to explicitly show time if it can be infered.
    # Proof:
      Φₙ†Φₘ
      Φ-ₙΦₘ
      e[iω(n+½)t - iω(m+½)t]
      e[-iω(m-n)t]
      φₘ-ₙ

    Φ⁰ = 1	# Don't have to explicitly show quantum number if it can be infered.
    Φⁱ = e[-iω(n+½)]
    Φᵗ = (Φⁱ)^t = e[t * (-iω(n+½))] = e[-iω(n+½)t]	# Just to show that the notation makes sense.

## Φ→φ

    Φₙ†Φₙ+₁ = φₙ+₁-ₙ = φ₁
    φ↥ ≡ φ₀↑ = φ₁	# This will make notation very consistent later.
    Φₙ†Φₙ+₁ = φ↥

    Φₙ†Φₙ-₁ = φₙ-₁-ₙ = φ-₁	# Yeah... me worry about this one a little bit!  LOL
    φ↧ ≡ φ₀↓ = φ-₁
    Φₙ†Φₙ-₁ = φ↧

    Φₙ†Φₙ+₂ = φₙ+₂-ₙ = φ₂
    Φₙ†Φₙ-₂ = φₙ-₂-ₙ = φ-₂

# sₙ, cₙ
Short for Sine(nωt) and Cosine(nωt):

    sₙ ≡ S[nωt]
    cₙ ≡ C[nωt]
    c₂ₙ=1-2s²ₙ	# Cosine double angle in terms of c and s.

    φₙ = cₙ-isₙ	# φ in terms of c and s.

    φ₁ = c₁-is₁

    φ-₁ = c₁+is₁	# Maybe that'll work.

    φ₁ + φ-₁ = 2c₁
    φ↥ + φ↧ = 2c₁	# Remember this one!

    φ₁ - φ-₁ = 2s₁
    φ↥ - φ↧ = 2s₁

    φ₂ = c₂-is₂
    φ-₂ = c₂+is₂

    φ-₂ + φ₂ = 2c₂
    φ↧↓ + φ↥↑ = 2c₂	# And remember this one!

## nᵒ
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
    nᵒ = u	# As expected.  :)

## L Σ[n(n-1)Pₙ]

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
    u²(0 + 0 + L[Σ[0,M-2]{n|Pₙ}])	      # 1/u! = 0 if integer u < 0
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

## p→P

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

## ξ
The non-dimensional displacement, ξ.

    ξ² ≡ mω/ħ x²   # A.1b
    x² = ħ/(mω) ξ²

## Aₙ
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
    Aₙ-₁ = Aₙ   * √[2n]	      # Decrement index n

    # With Whatchamacallits
    Aₙ   = Aₙ-₁ * √[½n-₁] = Aₙ-₁ * √[½n↓] = Aₙ-₁ * √[½n↓]
    Aₙ+₁ = Aₙ   / √[2n₁]  = Aₙ   / √[2n↑] = Aₙ   / √[2n↑]
    Aₙ   = Aₙ+₁ * √[2n₁]  = Aₙ+₁ * √[2n↑] = Aₙ+₁ * √[2n↑]
    Aₙ-₁ = Aₙ   / √[½n-₁] = Aₙ   / √[½n↓] = Aₙ   / √[½n↓]

    # Use these:
    Aₘ = √[2m↑]Aₘ↑ = √[½m↓]Aₘ↓

## ℋₙ
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

## Ψₙ
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

## ξΨₘ
Motivation: I will be calculating <Ψ|ξ|Ψ> later.

    ξΨₘ = ½Aₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
    # Proof:
      ξΨₘ
      ξAₘℋₘ[ξ]e[-ξ²/2]
      Aₘ ξℋₘ[ξ]e[-ξ²/2]
      Aₘ ½(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))
      ½Aₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))

## &lt;ξ&gt;
Evaluation of `<ξ>`:

    <ξ> = <Ψ|ξ|Ψ>             # 7.14a
    <ξ> = <Ψ|n><n|ξ|m><m|Ψ>   # 7.14b

    <ξ> = ΣΣ (pₙΨₙ)† ξ (pₘΨₘ)
    <ξ> = ΣΣ Ψₙ†pₙ pₘξΨₘ                                          # rearrange, p is real.
    <ξ> = ΣΣ Ψₙ†pₙ pₘ ½Aₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))                  # substitute for ξΨₘ
    <ξ> = ΣΣ Ψₙ†pₙ ½Aₘ(pₘℋₘ↑[ξ] + pₘℋₘ↓[ξ]/(½m↓))                 # distribute pₘ
    <ξ> = ΣΣ[pₙΨₙ†pₙ ½Aₘpₘℋₘ↑[ξ]] + ΣΣ[Ψₙ†pₙ ½Aₘpₘℋₘ↓[ξ]/(½m↓)]   # separate
    <ξ> = ½ΣΣ[Ψₙ†pₙ pₘ Aₘℋₘ↑[ξ]] + ½ΣΣ[Ψₙ†pₙ pₘ Aₘℋₘ↓[ξ]/(½m↓)]   # take out ½
    # get the m's to match
    <ξ> = ½ΣΣ[Ψₙ†pₙ √m↑pₘ↑/√nᵒ √[2m↑]Aₘ↑ℋₘ↑[ξ]] + ½ΣΣ[Ψₙ†pₙ √[nᵒm↓]pₘ↓ √[½m↓]Aₘ↓ℋₘ↓[ξ]/(½m↓)]
    <ξ> = 1/√[2nᵒ]ΣΣ[Ψₙ†pₙ m↑pₘ↑Aₘ↑ℋₘ↑[ξ]] + √[½nᵒ]ΣΣ[Ψₙ†pₙ pₘ↓Aₘ↓ℋₘ↓[ξ]]
    <ξ> = 1/√[2nᵒ]ΣΣ[Ψₙ†pₙ m↑ pₘ↑Ψₘ↑] + √[½nᵒ]ΣΣ[Ψₙ†pₙ pₘ↓Ψₘ↓]
    <ξ> = 1/√[2nᵒ]Σ[Ψₙ†pₙ n pₙΨₙ] + √[½nᵒ]Σ[Ψₙ†pₙpₙΨₙ]           # Orthogonal states
    <ξ> = 1/√[2nᵒ]ΣΣ[nPₙ] + √[½nᵒ]Σ[Pₙ]                          # Ψₙ†Ψₙ=1, pₙpₙ=Pₙ
    <ξ> = 1/√[2nᵒ]nᵒ + √[½nᵒ]
    <ξ> = √[½nᵒ] + √[½nᵒ]
    <ξ> = 2√[½nᵒ]
    <ξ> = √[2nᵒ]
    <ξ>² = 2nᵒ   # OK, need time development

    ... # TODO

    # Who want's to work with this horrible mess?
    <ξ> = √½Σ (e[-iω(n+½)t] √[uⁿe[-u]/n!])† (
      e[-iω((n+1)+½)t] √[n+1] √[u^(n+1)e[-u]/(n+1)!] +
      e[-iω((n-1)+½)t] √n √[u^(n-1)e[-u]/(n-1)!])
    <ξ> = √½Σ Φₙ†pₙ† (Φₙ+₁√[n+1]pₙ+₁ + Φₙ-₁√npₙ-₁)    # 7.20
    <ξ> = √½Σ Φₙ†pₙ (Φₙ+₁√n₁pₙ+₁ + Φₙ-₁/√n-₁pₙ-₁)     # Using Whatchamacallit, † does nothing to p.
    # Much nicer, no?
    <ξ> = √½Σ Φ†p (Φ↑√n↑p↑ + Φ↓/√n↓p↓)                # Context n, and arrow operators.  :)
    <ξ> = √½Σ Φ†Φ↑√n↑pp↑ + Φ†Φ↓/√n↓pp↓                # Distribute
    <ξ> = √½Σ √n↑pp↑Φ†Φ↑ + 1/√n↓pp↓Φ†Φ↓               # Rearrange
    <ξ> = √½Σ √n↑pp↑φ↥ + 1/√n↓pp↓φ↧                   # Φ→φ
    <ξ> = √½Σ √n↑ √nᵒ P/√n↑ φ↥ + 1/√n↓ P/√[nᵒn↓] φ↧   # p->P
    <ξ> = √½Σ √nᵒ P φ↥ + 1/n↓ P/√nᵒ φ↧                # Simplify
    <ξ> = √½Σ √nᵒ P φ↥ + n P/√nᵒ φ↧                   # 1/n↓ = n
    <ξ> = √½(Σ[√nᵒ P φ↥] + Σ[n P/√nᵒ φ↧])             # Separate the sums
    <ξ> = √½(√nᵒφ↥ΣP + φ↧/√nᵒΣ[nP])                   # Take out the constants
    <ξ> = √½(√nᵒφ↥(1) + φ↧/√nᵒ(nᵒ))
    <ξ> = √½(√nᵒφ↥ + φ↧√nᵒ)                           # :)
    <ξ> = √[½nᵒ](φ↥ + φ↧)
    <ξ> = √[½nᵒ](2c₁)                                 # φ↥+φ↧=2c₁, remember?
    <ξ> = √[2nᵒ]c₁
    <ξ>² = 2nᵒc²₁
    <ξ>² = 2nᵒ:Cosine²[nωt]

This time I got c₁ instead of <ξ>=√[2nᵒ]s₁ and <ξ>²=2nᵒs²₁.  Why?
It may be that 25 years ago I was not careful enough with φ₁ and φ-₁.
In fact, I've already noted in my revision that I messed up my treatment of 1ₙ (now Φₙ).
OK, so that's one of the major errors I was concerned with.
Let's see what happens to <ξ²>.
Expect a related error in <ξ²>, this is not the second error I'm looking for.

## &lt;ξ²&gt;
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

## Results
7.5 Results:

    Δ²ξ = <ξ²> - <ξ>²
        = (½ + 2nᵒc²₁) - 2nᵒc²₁
        = ½
