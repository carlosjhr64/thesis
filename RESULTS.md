### [CONTENTS](CONTENTS.md)

### 7.4 [The Related Programming Problem](RELATED.md)

> Previous results...

    <y> = Σₙ 1ₙ† pₙ†/√2 (1ₙ+₁ pₙ+₁ √[n+1]  +  1ₙ-₁ pₙ-₁ √n)   # 7.20
    pₙ = (-i)ⁿ e^(-½nᵒ) nᵒ^(½n)/√n!                           # 7.29

## 7.5 Results

Substituting this solution of `pₙ` into the series for `<y>`(7.20), I obtain

    <y> =                                                      # 7.31
    1/2^½ Σₙ (c₁+is₁)[n+1]^½pₙ†pₙ+₁ + (c₁-is₁)n^½pₙ†pₙ-₁,

    <y> =                                                      # 7.31b
    1/2^½ Σₙ -i(c₁+is₁)[nᵒ]^½pₙ†pₙ + i(c₁-is₁)pₙ†pₙn/[nᵒ]^½,

    <y> = (2nᵒ)^½sin[ωt].                                      # 7.31c

Likewise, for the series of `<y²>`(7.21) I obtain

    <y²> = (nᵒ+½) + nᵒsin[2ωt].                                # 7.32

And thus, evaluating the uncertainty in y,

    d²[y] = <y²> - <y>²
    d²[y] = (nᵒ+½) + nᵒs₂ - 2nᵒs²₁                             # 7.33a

But `nᵒ+nᵒsin[2ωt]=2sin²[ωt]`:

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
