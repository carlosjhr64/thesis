## Formulation of the Programming Problem

The problem I have set for myself is to maximize the knowledge of
the position `x` and momentum `p` of a particle of finite average energy `Eᵒ`.
Let `d[x]` and `d[p]` be the operators for the uncertainty in `x` and `p`, and
let `[Y>` be the state of a particle.
Then, I want to

    minimize <Y]d[x]d[p][Y>    # 5.1a
    subject to <Y]H[Y> = Eᵒ,   # 5.1b

where `H` is the Hamiltonian(energy) operator.

> Please do not confuse this with the ground state `E₀`.
> Later I explain that I'm looking for an optimal state `Yᵒ` with average energy `Eᵒ`.

That `<Y][Y>=1` is implicit.
This problem is called a mathematical programming problem.
The argument to be minimized is called the objective function~~(4.1a)~~*(5.1a)*, and
is followed by its constraints~~(4.1b)~~*(5.1b)*.

> My draft had an uncaught error.
> I'm talking about the two equations above in this section.
> The UCSC copy probably has the same error.

From the uncertainty principle, I know that for any state `[Y>`;

    <Y]d[x]d[p][Y> ≥ h/(4π).   # 5.2

I conjecture that there exist some state `[Yᵒ>` such that the above inequality becomes an equality,
and that this state is the optimum solution to the programming problem stated above.
Any state `[Y>` can be built from a superposition of eigen-states `[n>`.
Therefore, the programming problem can be expanded out to

    min <Y][n><n]d[x]d[p][m><m][Y>   # 5.3a
    sub <Y][n><n]H[m><m][Y> = Eᵒ     # 5.3b

> I really, really, hope that today any mathematician will recognize this can be done.
> As I recall
> I was not sure I could do this until I read the KKT paper.
> Then I was pretty sure I could do this.
> I guess it could have been that the distribution I picked would not work.
> I just knew that the Poisson distribution would work.
> What else could it be!?
> But I had no idea how much algebra there would be.
> Wow!
> It was a lot!

The benefit of this expansion is that it arithmetizes[⁷](REFERENCE.md) the problem.
The general idea of finding the minimum of a function is
to find some point from which any deviation increases the function.
The component eigen-states of the state `[Y>` gives me the ability to enumerate
the infinite amount of ways I can very state `[Y>`.

What I am varying in the state of the particle is its distribution of energy eigen-states.
Upon measurement, the probability of a particle having energy Eₙ is given by `<n][Y><Y][n>`.
Furthermore, the following properties make `<n][Y><Y][n>` a distribution function of n:

    0 ≤ <n][Y><Y][n> ≤ 1    # 5.4a
    <Y][n><n][Y> = 1        # 5.4b
    <Y][n><n]Eₙ[Y> = Eᵒ     # 5.4c

It is important to note that once the particle's energy has been measured to be Eₙ,
consequent measurements of the energy are certain to be the same Eₙ.
What happens is that a particle originally in a state of uncertain energy `[Y>`
collapses upon measurement into one of its energy eigen-states `[n>`.

> I want to point out that often we speak too loosely about quantum particles,
> as if we are following them around seeing them collapse somewhere.
> Anything we get to actually follow around behaves classically.
> In QM experiments we create an event here and
> then observe an event there and in between who knows?

## [An Intuitive Guess to the Optimum Distribution](INTUITIVE.md)
