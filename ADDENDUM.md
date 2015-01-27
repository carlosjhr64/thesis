## ADDENDUM

This was not in my original thesis.
Here I review stuff I've forgotten and needed to review.

### Mass On A Spring

My concern here was the possibility of complex amplitudes as
a solution to the mass on a spring problem.
I don't think an actual derivation exists.
One just conjures up a function, `x=F[t]`, with certain attributes `F[t, α, β, ⋯]`.
Let's see what happens:

```
m:Dt[:Dt[x]] = -kx                     # Given
# working with the second derivative with time
mDDx = -kx                             # D :: :Dt[]
DDx = (-k/m)x                          # /m
DDF[t, α, β, ⋯] = (-k/m)F[t, α, β, ⋯]  # b/c Hocus pocus.. puff... there it is!
αDF[t, α, β, ⋯] = (-k/m)F[t, α, β, ⋯]  # b/c I said so
α²F[t, α, β, ⋯] = (-k/m)F[t, α, β, ⋯]  # b/c I say so again
α² = (-k/m)                            # Oh! I know what α is! Do you?
:Dt[F[t, α]] = αF[t, α]                # We're looking for a function that looks like this
F[G[t, α]] :: F[t, α]                  # A composite?
D[F[G[t, α]]]                          # Find the derivative
D[F[G[t, α]]] = D[G[t, α]]F[G[t, α]]]  # b/c I say so?
D[G[t, α]] = α
∫D[G[t, α]] = αt ⋯?
G[t, α] = αt ⋯?                        # OK, so maybe I threw out the β too soon
G[t, α, β] = αt+β
F[αt+β]                                # Still looking for F (as if we didn't know already)
DF[αt+β] = αF[αt+β]
```

It's beginning to look like all I'm doing is guessing solutions.
Maybe if I just called `F[]` `e^()` and pretend to have solved something:

```
:Dt[e^(αt+β)] = αe^(αt+β)
DD[e^(αt+β)] = α²e^(αt+β)
α²e^(αt+β) = (-k/m)x       # Remember the original problem
x=e^(αt+β), α=√(-k/m)
```

Oh, boy!
Solving for the mass on the spring problem I get an exponetial and
a square root of a negative number.
What garbage!
I think maybe I gave `F[]` the wrong name.
Let's try `:Sine[]` (or `:Cosine[]`).

```
x=:Sine[αt+β]
DDx = :Dt[:Dt[:Sine[αt+β]]]
DDx = :Dt[α(:Cosine[αt+β])]
DDx = αDt[:Cosine[αt+β]]
DDx = -αα(:Sine[αt+β])
DDx = -α²:Sine[αt+β]
DDx = (-k/m)x                # original problem
-α² = (-k/m)
α² = (k/m)
```

`:Sine` gives a meaningful answer.
But how can `F` be both `e` and `:Sine`?

I don't think there's a way around the issue.
I know `e`, `:Sine`, and `:Cosine` have `F`'s properties via a search of functions I know.
Otherwise, it's just F[αt+β].  I might suspect the following:

```
F[α₀t+β₀] = :Sine[αₛt+βₛ] = :Cosine[αt+β] = e^(αₑt+βₑ) # WUT? No c subscript?
```

And that there must be a way to relate the different `[α, β]`.
I look in a book(something we used to read from containing lots of paper)
where a mathematician has written and proven the following: 

```
e^(a+bi) = (:Cosine[b] + i:Sine[b])e^a
```

And because I've had enough of this already, I say "Ah... I get it."
So I think I'm now past my original concern.
The general solution is in the Complex space.
