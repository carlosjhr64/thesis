## Measure of Uncertainty

The uncertainty principle states that there is a limit to
our ability to simultaneously measure a particle's position and momentum.
The uncertainty principle is often explained by pointing out that
in order to measure a particle's position and momentum
some form of contact must be made with the particle.
But the uncertainty principle is more that just our inability to measure
without our affecting what we are measuring.
The uncertainty principle is an intrinsic part of the particle.
If one could ask the particle wher it is and how fast it is going,
it would respond "I don't know!".

> Please understand that we were instructed to explain what we thought about our equations.

The question I want to ask Quantum Mechanics in this section is,
"How uncertain is the particle of its position and momentum, or any other observable?"
First, I have to mathematically define uncertainty.
The uncertainty in an observable is the variance of that observable.
Let `A` be the observable being measured.
Le `<A>` be the average value of `A`.
Then the uncertainty of `d[A]` in `A` is defined to be

    d²[A] ≡ <(A - <A>)²>   # 4.1a
    d²[A] = <A²> - <A>²    # 4.1b

If x is the position, and p is the momentum,
the uncertainty principle in terms of variaces is given by

    d[x]d[p] ≥ h/(4π)   # 4.2

where `h` is the Plank's constant.
Therefore, if one of either `d[x]` or `d[p]` is made small compared to `h/(4π)`,
the other is made large.

> It just dawned on me that it might upset some people that here
> I'm enumerating my equations with a pound sign instead of parenthesis as in the UCSC copy.
> OK, so in the UCSC copy, such labels are slightly raised above the line.
> Here, such people might confuse the label as part of the equation.

Within the mathematical rigor of Quantum Mechanics,
the uncertainty principle comes from
the commutator relation between the position and momentum operators.[⁸](REFERENCE.md)
An operator is a set of transformations on a state of particle,
to obtain the information that operator represents.
The state of a particle contains all knowable information about the particle, and
it is a solution to the Schrodinger equation for the potential in wich the particle is.
Let `A` and `B` be operators, and let `[Y>` be a state.
The commuatator is defined to be

    [A,B][Y> = AB[Y> - BA[Y>   # 4.3

The commutator is not necessarily zero since the set of instructions in `A` and `B` may not commute.
The order in which one operates on a state makes a differece.
Let `x` and `p` be the position and the momentum operators.
Then the uncertainty principle is given by the commutator relation

    [x,p] = ih/(2π)   # 4.4

where `i` is the imaginary number, square root of negative one.

> The very, very, imaginary number `i`.
> I never believed in `i`.
> Not in high-school.
> Not here.
> And not now.
> You want to say `i` is actually `[0,1]` with special rules of arithmetic?
> Fine.
> But there's no such thing as √(-1).
> So what's `#4.4`?
> Good question!
> Keep in mind that at the end of all calculations we are getting Real numbers.
> It is a calculating machine.
> I believe that wherever we find `i`, we are being given a HUGE hint.
> But what is it really?
> NO! IT IS NOT √(-1).
