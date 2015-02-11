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

> Eventually I hope to have the entire work in one stream of "mathematical code".
> For now I think I'll work my way backwards, back and forth.

> In books you'll see `sin²(x)` to mean `sin(x)*sin(x)`,
> I'll use that convention in general.
> `u²[v]` will mean `u[v]*u[v]` and not `u[u[v]]`.

```
# How to read:

uⁿ[v] ≡ (u[v])ⁿ
u²[v] ≡ u[v]*u[v]
uᵐₙ ≡ (uₙ)ᵐ              # I'm leaving uₙ² undefined, but it's probably u[n²].

# Trivial Definitions:

u=u                      # Just kidding, we won't be starting from there.  :))
N ≡ Σₙ 1                 # If we happen to mention N, this is what it is.
<u> ≡ Σₙuₙ/N             # What we mean by average value.

# P is a distribution. Later, specifically a Poisson distribution:

Σₙ Pₙ = 1
0 ≤ Pₙ ≤ 1
<u> = ΣₙPₙuₙ

# Measure of uncertainty defined (4.1a):

d²[u] ≡ <(u - <u>)²>
d²u ≡ <(u - <u>)²>       # Allow the shorter form if unambiguous.

d[u] ≡ √[d²u]            # I only defined d² and a not in terms of d, so...
du ≡ √[d²u]              # Again, allow the shorter form.

# Deriving 4.1b:

d²u = <u² - 2u<u> + <u>²>
d²u = <u²> - 2<u><u> + <u>²
d²u = <u²> - 2<u>² + <u>²
d²u = <u²> - <u>²

# Measure of uncertainty (4.1b):

d²u = <u²> - <u>²

# Fundamental values spring constant k and mass m:

R{k,m}                   # k and m are measured or given Real numbers.

# Derived values frequency, f, and angular frequency, ω:

ω² ≡ k/m
ω = √[k/m]

f ≡ ω/(2π)

# The Imaginary number i:

i ≡ √[-1]                # Whatever!  LOL
i ≡ [0,1] : i²=[1,0]     # Yea, don't expect to re-implement this into QM anytime soon.
i² ≡ -1                  # I think the best definition of "i" for now.

# Sine and Cosine:

S[u] ≡ :Sine[u]
C[u] ≡ :Cosine[u]

sₙ ≡ S[nωt]
cₙ ≡ C[nωt]

# Trigonometric Identities:
# http://en.wikipedia.org/wiki/List_of_trigonometric_identities

S²+C²=1                  # Pythagoras
S[u+v]=SuCv+CuSv         # Sine's angle sum
C[u+v]=CuCv-SuSv         # Cosine's angle sum
C[2u]=1-2S²u             # Cosine double angle "cos(2u)=1-2*sin²(u)"
c₂ₙ=1-2sₙ                # Cosine double angle in terms of c and s.

# Just a quick exercise.
# Derivation: Cosine's Angle Sum to Cosine Double Angle:

C[2u] = C[2u]
C[2u] = C[u+u]
C[2u] = C[u]C[u]-S[u]S[u]
C[2u] = C²-S²
C[2u]-1 = C²-S²-1
C[2u]-1 = (C²-1)-S²
C[2u]-1 = (-S²=C²-1)-S²  # A bit of "rubyism" here.  Just invoking Pythagoras.
C[2u]-1 = -S²-S²
C[2u]-1 = -2S²
C[2u] = 1-2S²

# The Exponential function:

e[u] ≡ :Exponential[u]   # This is normally just e^u. Here, e is the operator and not the number.
eᵘ ≡ e^(u) ≡ e[u]        # Allow the classic forms of the Exponential function.

# Known properties of e:

e[u]e[v] = e[u+v]
e[iu] = C[u]+iS[u]
e[-iu] = C[u]-iS[u]

# TODO: nᵒ

# TODO: <y>²:

...
<y> = √[2nᵒ]s₁
<y>² = 2nᵒs²₁

# TODO: <y²>:

...
<y²> = (nᵒ+½) - nᵒc₂

# 7.5 Results:

d²y = <y²> - <y>²
d²y = (nᵒ+½) - nᵒc₂ - 2nᵒs²₁         # 7.33a: Subtitute in previous results.
d²y = (nᵒ+½) - nᵒ(1-2s²₁) - 2nᵒs²₁   # Cosine double angle formula.
d²y = ½                              # 7.33b.

```
