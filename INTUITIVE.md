### [TABLE OF CONTENTS](CONTENTS.md)

### 5. [Formulation of the Programming Problem](FORMULATION.md)

## 6. An Intuitive Guess to the Optimum Distribution

In this section, I show why the Poisson distribution is a good guess
for an optimun distribution to minimize uncertainties for the simple harmonic oscillator.
The Poisson distribution is given by

    Pₙ = uⁿe^(-u)/n!,   # 6.1

where `u` is the average value of the distribution,
`n` is a non-negative integer value, and
`Pₙ` is the probability of observing a value of `n`.
The Poisson distribution approaches a Gaussian distribution for large `u`, and
is known to have a standard deviation of the square root of `u`.

> Notice that for equation 6.1 I'm unable to reproduce the superscript notation for `e^(-u)`.
> But I want to give my opinion that the solution
> isn't to clutter up our table of symbols with more symbols.
> We only have ten fingers and limited landscape on a keyboard.
> Top priority should be to be able to write fluidly what we need to write.
> So I argue that we should strive for a new notation more suitable to our current tools, and
> leave behind the legacy of pen and paper.
> Note that you'll still be able to write the new notation with pen and paper!

The problem of evaluating uncertainties is in the same spirit as error analysis.
When taking measurements, random errors creep in.
Thus, the measurements will differ from some average value.
This leads to a Guassian distribution of measurements centered about an ideal value.

> Just a bit of a tangent.
> The things we're measuring do not live on a coordinate system
> sitting nicely at some point where we get to read off [a,b,c].
> We say... "This looks like a foot, three inches, and say three quarters."
> We're truncating what to us really does look like Real numbers.
> The chances that what we are measuring is commesurable with a given arbitrary unit is dismal.

When one measures the energy of a simple harmonic oscillator,
these measurements will also differ from the expected value of the energy.
But these measurements cannot belong to a Gaussian distribution because
they can only have positive discrete values.
Still, on the scale of large energies,
the interval between energy values becomes small enough that
one may consider the energy to be continuous, and
the probabilities for near zero energy values are very small.
Then, if the uncertainty in the energy of a simple harmonic oscillator is due to
random deviations from the average,
one might expect the distribution of energy measurements to approach
the Gaussian distribution as the average energy increases.

> There may be one gnawing issue for mathematicians though.
> One can see how a sequence of numbers aproaches a limit number.
> But a discrete system never aproaches continuity... it is just always discrete.
> How big of a monkey wrench is that?
> It does not bother me one bit!
> :))

Due to the symmetry between the position's and momentum's contribution to the energy,
I expect the optimum uncertainty in the position to be the same as that for the momentum.
Since the energy is given by

    E = ½p²/m + ½kx²,   # 6.2

then through calculus the uncertainty in `E` is given by

    d[E] = pd[p]/m + kxd[x].   # 6.3

> Recall that `d[]` is defined in [4.1](UNCERTAINTY.md).
> This is a standard trick in error analysis.
> Notice how it makes `d[x]` look like `dx`... I'm so clever!

To minimize `d[E]`, one differentiates `d[E]` and sets it to zero to obtain

~~d[p]/m = kd[x]~~

    d²[E]/m = kd²[x]   # 6.4

where the sign is ignored since only the magnitude of the values are relevant.
I conjectured earlier that
the optimum solution to minimize the uncertainties occurred when `d[x]d[p]=h/(4π)`.
This conjecture leads me to expect

~~kd[x] = d[p]/m = ½ωSQRT[h/π].~~

    kd²[x] = d²[p]/m = ½ωSQRT[h/π].   # 6.5

> We sometimes forget that what seems obvious is not always that trivial.
> Equation 6.5 is justified by the
> [Equipartition theorem](http://en.wikipedia.org/wiki/Equipartition_theorem).
> Deviations in position means deviation in potential energy.
> Deviations in momentum means deviation in kinetic energy.
> 6.5 says errors are just as likely on either side.
> My draft had penciled in a couple of corrections.
> I'm pretty sure the UCSC copy is correct, though.
> Note that here, `SQRT[]` means `√[]`, the square-root.

Since `d[x]` and `d[p]` are independent random errors,[⁶](REFERENCE.md)
the uncertainty in the energy `d[E]` is better given by

    d[E] = SQRT[(pd[d]/m)² + (kxd[x])²].   # 6.6

Then by substituting in for `d[x]` and `d[p]`, I obtain

    d[E] = SQRT[(½p²/m + ½kx²)½hω/π].   # 6.7

But in Quantum Mechanics, one works with expectation values of observables.
Thus the previous expression(6.7) changes to

    d[E] = SQRT[(½<p²>/m + ½k<x²>)½hω/π].   # 6.8

For the simple harmonic oscillator, it is well known that

    ½<p²>/m = ½k<x²> = ½E.   # 6.9

> This says that everage value of the kinetic energy is the same as
> the average value of the potential energy, which is half the total energy.
> Well known fact?
> I sort of remember this being covered in class at some point,
> but I can't find the specific reference to it now.
> Apparently it's a consequence of the more general
> [Virial theorem](http://en.wikipedia.org/wiki/Virial_theorem),
> which I have no memory of ever studying, but it's in the college text book.
> Anyways, the derivation is quick enough:

    # I get to use my notation b/c I'm old and don't give a damn.
    V = ½kx²                                 # Given the harmonic potential,
    <V>=(1/tᵒ)∫[0,tᵒ]{t|V}                     # find the time average of the potential energy.
    # The integral operator takes two variables and a block, right?
    # The block is evaluated from 0 to tᵒ.
        (1/tᵒ)∫[0,tᵒ]{t|½kx²}
        (1/tᵒ)∫[0,tᵒ]{t|½k(A:Sine[ωt])²}
        ½kA²(1/tᵒ)∫[0,tᵒ]{t|S²[ωt]}          # S:::Sine implicitly
    E=½kA²                                   # Note the total energy.
    <V>=E(1/tᵒ)∫[0,tᵒ]{t|S²[ωt]}
        E/tᵒ∫[0,tᵒ]{t|S²[ωtᵒ]}
    u:=ωt                                    # Let...
    t=u/ω,du=ωdt,dt=du/ω                     # Consequences of change of variables.
    <V>=Eω/uᵒ∫[0,uᵒ]{u|S²[u]/ω}              # Implementing change of variables.
        E/uᵒ∫[0,uᵒ]{u|S²[u]}
    # Circular functions are tricky.
    # Just want to go from minimum to maximum once.
    <V>=E/(π/2)∫[0,π/2]{u|S²[u]}             # Half period.
        2E/π∫[0,π/2]{u|S²[u]}
        2E/π[0,π/2]{½(x-S[u]:Cosine[u])}     # By Wolframalpha, see link below.
        E/π[(π/2-S[π/2]C[π/2])-(0-S[0]C[0])] # C:::Cosine implicitly
        E/π[(π/2)-(0)]
        (E/π)(π/2)
        E/2
    <V>=½E # Like said, obviously!  :P

> [Wolframalpha](http://www.wolframalpha.com/input/?i=Integral+sin%28x%29%5E2+dx)

Hence, I expect the optimum uncertainty in the energy to be

    d[E] = SQRT[½hωE/π]   # 6.10

> Since I was a bit thrown off by this at first sight, I'll derive it:

    d[E] = SQRT[(½<p²>/m + ½k<x²>)½hω/π]   # 6.8
    d[E] = SQRT[(½E + ½E)½hω/π]
    d[E] = SQRT[E½hω/π]
    d[E] = SQRT[½hωE/π]

> It's the square-root of energy squared.

To summarize, I have shown that
I expect the discrete distribution of the energy measurements for the simple harmonic oscillator
to approach a Gaussian distribution for large energies, and that
I expect the standard deviation for the distribution to grow
as the square root of the average energy.
The Poisson distribution fulfills all of these expectations, and therefore,
it is a good guess for an optimum distribution.[⁵](REFERENCE.md)

> After the above paragraph I have in pencil the following:

    since E ~ hωn/(2π),
    d[e] = hω/(2π)SQRT[n]

> I don't know if I add that on the UCSC copy.
> It's just a re-iteration of 6.10 for the QM version.

## 7. [Solving the Programming Problem](SOLVING.md)
