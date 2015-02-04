### [TABLE OF CONTENTS](CONTENTS.md)

### 6. [An Intuitive Guess to the Optimum Distribution](INTUITIVE.md)

## 7. Solving the Programming Problem

In section five of this paper,
I formulated the problem of minimizing the uncertainty
in both the position and momentum of a particle
as a mathematical programming problem.

    min <Y][n><n]d[x]d[p][m><m][Y>   # 7.1a
    sub <Y][n><n]Eₙ[n><n][Y>         # 7.1b

Note that the constraint equation differs from that([5.3b](FORMULATION.md))
in section 5 for this paper.
Since the energy operator `H` is Hermitian, there are no cross products.
Therefore, the simple substitution of `H` to `Eₙ` is allowed.

Although the above set of equation is terse,
obtaining a solution is very involved.
This is because of the operators `d[x]` and `d[p]`.
There are many steps involved in evaluating `d[x]` and `d[p]`.
I will first evaluate `d[x]`, and it will be noted that the evaluation of `d[p]`
closely parallels that of `d[x]`.

> There was of course a deadline.
> Not that a deadline meant much to a guy on his 7th year working towards a B.A.
> But I really wanted to get this over with.

The evaluation of `d[x]` will take two steps.  From the definition

    d²[x] = <x²> - <x>²,

I will first evaluate `<x²>`, and then `<x>²`.
Also, to reduce the number of symbols to be manipulated,
I will work with the unitless operators of position and momentum as defined by

     y² = (2πmω/h) x²,         # 7.3a

and

     q² = -2π/(hωm) (d/dx)².   # 7.3

> Note that 7.3a re-iterates 3.3b, and here I have `y²` correctly.
> [3.3b](QMSHO.md) really was a transcription error.
> So I am about to evaluate 7.1a, the objective function, or
> at least half way and argue symmetry (or equipartition) for the other half.

### 7.1 [Evaluation of `<y²>`](Y2.md)
