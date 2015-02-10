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
# Trivial Definitions:

u=u                      # u is an arbitrary symbol, and... just kidding, we won't be starting from here.  :))
N ≡ Σₙ 1                 # If we happen to mention N, this is what it is.
<u> ≡ Σₙuₙ/N             # What we mean by average value.

# How to read...

uⁿ[v] ≡ (u[v])ⁿ
u²[v] ≡ u[v]*u[v]
uᵐₙ ≡ (uₙ)ᵐ              # Note that I'm leaving uₙ² undefined, but it would probably be something like u[n²].

# P is a distribution. Later, specifically a Poisson distribution:

Σₙ Pₙ = 1
0 ≤ Pₙ ≤ 1
<u> = ΣₙPₙuₙ

# Measure of uncertainty defined (4.1a):
d²[u] ≡ <(u - <u>)²>
d²u ≡ <(u - <u>)²>	 # Allow the shorter form if unambiguos.

d[u] ≡ √[d²u]            # Strictly speaking, I only defined d² and a not in terms of d, so...
du ≡ √[d²u]              # Again, allow the shorter form.

# Deriving 4.1b:
d²u = <u² - 2u<u> + <u>²>
d²u = <u²> - 2<u><u> + <u>²
d²u = <u²> - 2<u>² + <u>²

# Measure of uncertainty (4.1b):
d²u = <u²> - <u>²

# Fundamental values
# Spring constant k, mass m.

R{k,m}                   # k and m are typically measured values, Real numbers.

# Derived value
# Frequency f, Angular frequency ω.

ω² ≡ k/m
ω = √[k/m]

f ≡ ω/(2π)

# Sine and Cosine:

S[u] ≡ :Sine[u]
C[u] ≡ :Cosine[u]

sₙ ≡ S[nωt]
cₙ ≡ C[nωt]

# Some properties if S and C:
S²+C²=1
S[u+v]=SuCv+CuSv

The Imaginary number i:

i ≡ √[-1]                # Whatever!  LOL
i ≡ [0,1] : i²=[1,0]     # Yea, OK.  But don't expect me to re-implement this into QM anytime soon.
i² ≡ -1                  # Probably the best definition of "i" until we figure out what it really is in QM.

# The Exponential function:

e[u] ≡ :Exponential[u]   # This is normally just e^u.  Note that now e is the operator and not the number.

# Known properties of e
e[u]e[v] = e[u+v]
e[iu] = C[u]+iS[u]
e[-iu] = C[u]-iS[u]

# TODO: nᵒ

# 7.5 Results

# :-??
d²y = ½                  # 7.33b

```
