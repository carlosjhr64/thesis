### [CONTENTS](CONTENTS.md)

### 7.4 [The Related Programming Problem](RELATED.md)

> Previous results...

    <y> = Σₙ 1ₙ† pₙ†/√2 (1ₙ+₁ pₙ+₁ √[n+1]  +  1ₙ-₁ pₙ-₁ √n)                         # 7.20
    <y²> = (nᵒ+½) + ½Σₙ 1ₙ† pₙ† (1ₙ-₂ pₙ-₂ [n(n-1)]^½  +  1ₙ+₂ pₙ+₂ [(n+1)(n+2)]^½) # 7.21
    pₙ = (-i)ⁿ e^(-½nᵒ) nᵒ^(½n)/√n!                                                 # 7.29

## 7.5 Results

Substituting this solution of `pₙ` into the series for `<y>`(7.20), I obtain

    <y> =                                                      # 7.31
    1/2^½ Σₙ (c₁+is₁)[n+1]^½pₙ†pₙ+₁ + (c₁-is₁)n^½pₙ†pₙ-₁,

    <y> =                                                      # 7.31b
    1/2^½ Σₙ -i(c₁+is₁)[nᵒ]^½pₙ†pₙ + i(c₁-is₁)pₙ†pₙn/[nᵒ]^½,

    <y> = (2nᵒ)^½sin[ωt].                                      # 7.31c

Likewise, for the series of `<y²>`(7.21) I obtain

~~<y²> = (nᵒ+½) + nᵒsin[2ωt].~~

    <y²> = (nᵒ+½) - nᵒcos[2ωt].                                # 7.32

> The trig identity for 7.33b was obviously supposed to be `1-c₂=2s₁` and
> what I had instead was nonsense.
> The only time I see `2ωt` in my notes is with cosine.
> It's the only way I see this last step working.
> I now wish I'd just left this paper alone, but I didn't so...
> I'm going to try to reconstruct the entire work, in [The Full Monty](FULLMONTY.md).

And thus, evaluating the uncertainty in y,

    d²[y] = <y²> - <y>²
    d²[y] = (nᵒ+½) - nᵒc₂ - 2nᵒs²₁                             # 7.33a

~~But `nᵒ+nᵒsin[2ωt]=2sin²[ωt]`:~~

But `nᵒ-nᵒc₂=2nᵒs₁`:

    d²[y] = ½                                                  # 7.33b

By substituting the sine function with a cosine function, one obtains the results for the uniless momentum `q`.

> I remember that at the time this was all very clear in my mind.
> Much like any computer program I have ever written,
> while I'm actively working on it,
> every chunck of code is alive in my mind
> and I know where it all is...
> I can see here that I've not delivered the final punch line.
> What  is `<Yᵒ]d[x]d[p][Yᵒ>`?
> It is `ћ/2`!

### 8. [Conclusions and After Thoughts](CONCLUSIONS.md)
