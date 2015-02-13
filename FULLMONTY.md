### [CONTENTS](CONTENTS.md)

## The Full Monty

> This section was not in the original thesis.
> In my review of my own paper now 25 years later,
> I found mostly copy errors and typos which I hope I've mostly fixed.
> But I also found a couple of possibly serious errors.
> I want to first verify and expose where I went wrong by explicitly laying out all the work.
> Also, if I get a chance (and if possible), I'd like to get the UCSC copy, as I'm using what was a working draft.

Here I write explicitly all my work with little commentary, as if writting computer code.
Consider all symbols to have global scope.
Each symbol should only be defined once, except `u` and `v` which will be used as a temporary variables.

In books you'll see `sin²(x)` to mean `sin(x)*sin(x)`.
I'll use that convention in general.
`u²[v]` will mean `u[v]*u[v]` and not `u[u[v]]`.

I'm going to switch the notatation for the `1ₙ` object to `Φₙ`.
The reason I used `1ₙ` is that it is a kind of unit length object.
The reason I don't want to use `Iₙ` is that it migt be confused as a kind of identity object, which it is not.
To me, `Φₙ` looks like a one with a circle, which is kind of the right idea.

> BTW, it's possible that the reason I used the `<Y]` notation instead of `<Y|` is that
> I did not have the pipe symbol available at the time.  IDK.

> Eventually I hope to have the entire work in one stream of "mathematical code".
> For now I think I'll work my way backwards, back and forth.

```
# Arbitrary symbols

u=u,v=v	# Just kidding, we won't start from there.

# Integers

ℕ{0}	# I'm talking about ℕ that includes zero.
ℕ{N,n,m}	# N, M, n, and m are are like 0,1,2,3,...
M≡N-1	# It just simplifies notation later on.

# Please be aware that there is no actual parser checking my work and that
# I may inadvertently miswrite an expression.
# How to read:

uuu = ((uu)u)
u u u = (u(uu))
u!u = (u!)u

uⁿ[v] ≡ (u[v])ⁿ
u²[v] ≡ u[v]*u[v]
uᵐₙ ≡ (uₙ)ᵐ	# I'm leaving uₙ² undefined, but it's probably u[n²].

# Squares

u²≡uu

# Squareroot

√[u²]≡u
√[uu]=u

# Summation over indeces:

uₙ ≡ u[n]
Σₙ uₙ ≡ Σ[0,M]{n|u[n]}	# NOTE!  Indeces start with zero.
N = Σₙ 1

# N is very, very, big!
# When I say, "In the limit...", this is what I mean for a big enough N:

L[u+v] ≡ L[u] + L[v]
L[u] ≡ (|u| ≥ 1/N)? u : 0

# Examples:
L[u+1/N] = u
L[u+e[N]/N!] = u	# If you don't agree, you're not thinking of a big enough N. Try N≥8.
L[u+(v^N)/N!] = u	# Exactly at what point this is true depends on v, but at some point it's true.
L[u+e[-N]] = u	# Obviously, I hope.
|u| ≤ 1/N, |v| ≤ 1/N  ⇒  |uv| ≤ 1/N² ≤ 1/N, L[uv]=0

# Factorial:

n! ≡ Π[1,n]{u|u} # 1*2*3*...*n

# Average value

<u> ≡ Σₙuₙ/N	# What we mean by average value.

# Measure of uncertainty defined (4.1a):

d²[u] ≡ <(u - <u>)²>
d²u ≡ <(u - <u>)²> 	# Allow the shorter form if unambiguous.

d[u] ≡ √[d²u]	# I only defined d² and a not in terms of d, so...
du ≡ √[d²u]	# Again, allow the shorter form.

# Deriving 4.1b:

d²u = <u² - 2u<u> + <u>²>
d²u = <u²> - 2<u><u> + <u>²
d²u = <u²> - 2<u>² + <u>²
d²u = <u²> - <u>²

# Measure of uncertainty (4.1b):

d²u = <u²> - <u>²

# The Imaginary number i:

i ≡ √[-1]	# Whatever!
i ≡ [0,1] : i²=[1,0]	# Yea, don't expect to re-implement this into QM anytime soon.
i² ≡ -1	# I think the best definition of "i" for now.

# Sine and Cosine:

S[u] ≡ :Sine[u]
C[u] ≡ :Cosine[u]

# Trigonometric Identities:
# http://en.wikipedia.org/wiki/List_of_trigonometric_identities

S²+C²=1	# Pythagoras
S[u+v]=SuCv+CuSv	# Sine's angle sum
C[u+v]=CuCv-SuSv	# Cosine's angle sum
C[2u]=1-2S²u	# Cosine double angle "cos(2u)=1-2*sin²(u)"

# Just a quick exercise.
# Derivation: Cosine's Angle Sum to Cosine Double Angle:

C[2u] = C[2u]
C[2u] = C[u+u]
C[2u] = C[u]C[u]-S[u]S[u]
C[2u] = C²-S²
C[2u]-1 = C²-S²-1
C[2u]-1 = (C²-1)-S²
C[2u]-1 = (-S²=C²-1)-S²	# A bit of "rubyism" here.  Just invoking Pythagoras.
C[2u]-1 = -S²-S²
C[2u]-1 = -2S²
C[2u] = 1-2S²

# The Exponential function:

e[u] ≡ :Exponential[u]	# This is normally just e^u. Here, e is the operator and not the number.
eᵘ ≡ e^(u) ≡ e[u]	# Avoid these alternate forms?

# Known properties of e:

e[u]e[v] = e[u+v]
e[iu] = C[u]+iS[u]
e[-iu] = C[u]-iS[u]
e[0] = 1

# Complex conjugation:

(u+iv)† ≡ u-iv
e[i]† = (C+iS)† = C-iS = e[-i]	# what it does to e

# P is the Poisson distribution:
# http://en.wikipedia.org/wiki/Poisson_distribution

Pₙ ≡ uⁿe[-u]/n!
Σₙ Pₙ = 1
0 ≤ Pₙ ≤ 1
<u> = Σₙ Pₙuₙ

pₙ†pₙ ≡ Pₙ	# We're assuming this and see how it goes!
pₙ = √[uⁿe[-u]/n!]
# Proof
  pₙ†pₙ
  √[uⁿe[-u]/n!]†√[uⁿe[-u]/n!]
  √[uⁿe[-u]/n!]√[uⁿe[-u]/n!]	# It's just all real.
  uⁿe[-u]/n!
  Pₙ

# Fundamental values
# I think the point here is that these values are "measured" by "experiment" in "some way".
# "OK"

R{m}	# Mass
R{k}	# Spring contant 

# Derived values

ω² ≡ k/m	# Angular frequency
ω = √[k/m]

f ≡ ω/(2π)	# Frequency

Eₙ = ωħ(n+½)	# 3.2: Energy eigen-value

# Time evolution Φₙ thingy
# 7.17 TODO: why -iEₙt/ħ and not +iEₙt/ħ?

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

# Φ→φ:

Φₙ†Φₙ+₁ = φₙ+₁-ₙ = φ₁
Φₙ†Φₙ-₁ = φₙ-₁-ₙ = φ-₁	# Yeah... me worry about this one a little bit!  LOL

# Short for Sine(nωt) and Cosine(nωt).

sₙ ≡ S[nωt]
cₙ ≡ C[nωt]
c₂ₙ=1-2sₙ	# Cosine double angle in terms of c and s.

φₙ = cₙ-isₙ	# φ in terms of c and s.

φ₁ = c₁-is₁
φ-₁ = c₁+is₁	# Maybe that'll work.

# Average Quantum number nᵒ

nᵒ ≡ L <n>

<n> = <n|pₙ†npₙ|n> = Σₙ pₙ†npₙ = Σₙ nPₙ
    = Σₙ nuⁿe[-u]/n!				# Just by definition of <n>.
    = Σ[0,M]{n|nuⁿe[-u]/n!}			# Definition of Σₙ.
    = 0 + Σ[1,M]{n|nuⁿe[-u]/n!}			# The first element in the series is just zero.
    = Σ[1,M]{n|uⁿe[-u]/(n-1)!}			# Have the n factor absorbed by the factorial.
    = Σ[0,M-1]{n|u[n+1]e[-u]/n!}		# Shift.
    = uΣ[0,M-1]{n|uⁿe[-u]/n!}			# Take out a factor of u.
    = u(Σ[0,M]{n|uⁿe[-u]/n!} - (u^M)e[-M]/M!)	# Add and subtract the an Nth element (which is M).
    = u(ΣₙPₙ) - u(u^M)e[-M]/M!			# Definition of Σₙ and Pₙ.
    = u(1) - u^(M+1)e[-M]/M!			# Poisson distribution sums up to one.
    = u - u^(M+1)e[-M]/M!

nᵒ = L[u - u^(M+1)e[-M]/M!]
nᵒ = L[u] - L[u^(M+1)e[-M]/M!]
nᵒ = u - 0
nᵒ = u	# As expected.  :)

# Now we can describe the distribution in terms of the average quantum number:

Pₙ = nᵒⁿe[-nᵒ]/n!
pₙ = √[nᵒⁿe[-nᵒ]/n!]

# p→P:

pₙpₙ+₁ = √[nᵒⁿe[-nᵒ]/n!] √[nᵒ^(n+1)e[-nᵒ]/(n+1)!]
       = √[nᵒⁿe[-nᵒ]/n!] √[nᵒⁿe[-nᵒ]/n!] √[nᵒ/(n+1)] 
       = pₙ pₙ √[nᵒ/(n+1)] 
       = Pₙ √[nᵒ/(n+1)] 
pₙpₙ+₁ = √[nᵒ/(n+1)]Pₙ 

pₙpₙ-₁ = √[nᵒⁿe[-nᵒ]/n!] √[nᵒ^(n-1)e[-nᵒ]/(n-1)!]
       = √[nᵒⁿe[-nᵒ]/n!] √[nᵒⁿe[-nᵒ]/n!] √[n/nᵒ] 
       = pₙ pₙ √[n/nᵒ] 
       = Pₙ √[n/nᵒ] 
       = √[n/nᵒ]Pₙ 

# TODO: <y>²:

...
<y> = √½Σₙ Φₙ†pₙ† (Φₙ+₁√[n+1]pₙ+₁ + Φₙ-₁√npₙ-₁)	# 7.20
<y> = √½Σₙ Φₙ†pₙ†Φₙ+₁√[n+1]pₙ+₁ + Φₙ†pₙ†Φₙ-₁√npₙ-₁	# Distribute.
<y> = √½Σₙ √[n+1]pₙ†pₙ+₁Φₙ†Φₙ+₁ + √npₙ†pₙ-₁Φₙ†Φₙ-₁	# Rearrange
<y> = √½Σₙ √[n+1]pₙ†pₙ+₁φ₁ + √npₙ†pₙ-₁φ-₁		# Φ→φ
<y> = √½Σₙ √[n+1] √[nᵒ/(n+1)]Pₙ φ₁ + √n √[n/nᵒ]Pₙ φ-₁	# p→P, whose getting a little excited about now?
<y> = √½Σₙ √nᵒPₙφ₁ + n/√nᵒPₙφ-₁				# OK, something went wrong here?
# I think I know what's next, but good place to take a break.
...
<y> = √[2nᵒ]s₁
<y>² = 2nᵒs²₁

# TODO: <y²>:

...
<y²> = (nᵒ+½) + ½Σₙ Φₙ†pₙ† (1ₙ-₂√[n(n-1)]pₙ-₂ +  Φₙ+₂√[(n+1)(n+2)]pₙ+₂)	# 7.21
...
<y²> = (nᵒ+½) - nᵒc₂

# 7.5 Results:

d²y = <y²> - <y>²
d²y = (nᵒ+½) - nᵒc₂ - 2nᵒs²₁	# 7.33a: Subtitute in previous results.
d²y = (nᵒ+½) - nᵒ(1-2s²₁) - 2nᵒs²₁	# Cosine double angle formula.
d²y = ½	# 7.33b.

```
