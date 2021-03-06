# THE OPTIMUM DISTRIBUTION OF ENERGY EIGEN-STATES FOR THE SIMPLE HARMONIC OSCILLATOR
## A case study of a quadratic programming problem of infinite size.
### By Carlos J. Hernandez
### UCSC Senior Thesis, Spring 1990
### Revised 2015

> I've kept my notes from my thesis and thought
> I might enjoy rewritting it here,
> making it clearer if possible, and
> adding points I did not have time to put on the final submission.
> Looks like I don't have the actual final draft, but otherwise
> this should be very close to what I submitted, and then with added commentary.
> Also, there are some interesting scribles sprinkle throughout my notes,
> digressions I'll include for fun. Let's start with this one:
```
D[xˣ]=(L[x]+1)xˣ            # Prove this
u:=xˣ                       # Let
D[L[u]]                     # Consider derivative of logarithm of u
D[L[u]]=(1/u)D[u]           # Derivative of a logarithm
uD[L[u]]=D[u]               # *u
D[u]=uD[L[u]]               # We now have an expression for D[u]
D[xˣ]=xˣD[L[xˣ]]            # u -> xˣ
D[xˣ]=xˣD[xL[x]]            # A property of logarithms L[xⁿ]=nL[x]
D[xˣ]=xˣ(D[x]L[x]+xD[L[x]]) # Chain rule
D[xˣ]=xˣ(L[x]+x/x)          # D[L[u]]=(1/u)D[u]
D[xˣ]=xˣ(L[x]+1)            # x/x::1
D[xˣ]=(L[x]+1)xˣ            # Prefer the form: D[u]=f(u)u
```
[wolframalpha](http://www.wolframalpha.com/input/?i=d%2Fdx+x%5Ex)

> Looking at my scribles, I had the right idea and... somehow the right answer.
> Today, we have Wolfamalpha.com!

> While re-reading my thesis, the use of the word "paper" struck me as odd and
> thought that in another 25 years it might not make sense anymore.
> By "paper" I mean this thesis, this work.
> We used to write on this thing called "paper".

> There were a lot of copy errors and a couple of actual errors in my original thesis.
> You might want to skip right to the [full monty](FULLMONTY.md), work in progress,
> where I try to solve the problem without skipping any steps.

## ABSTRACT

A single energy eigen-state of the simple harmonic oscillator
leaves a particle uncertain in its position and momentum.
In this paper I minimize this uncertainty through a distribution of energy eigen-states.
I show that a Poisson distribution of energy eigen-states is a feasible solution because
it satisfies the constraints for a physically meaningful distribution, and that
it is the optimum solution because
it satisfies the necessary and sufficient conditions for a minimum in the uncertainty
in the particle's position and momentum.

> Talking about my thesis to others since,
> I've come up against misunderstandings from laypeople.
> One misunderstanding has been that I was violating the uncertainty principle.
> Quantum Mechanics(QM) does not say you can't minimize uncertainties.
> It does put a lower bound ΔxΔp≥ħ/2, above zero.
> Another misunderstanding comes from how in practice
> solutions to mathematical programming problems are found.
> I did not do a "search" for a solution in a quadratic programming problem of infinite size,
> I guessed the solution and proved by induction that it's optimal.
> If you get lucky and guess the solution, the solution is quickly verified.
> And my guess was not all that lucky... there's only one good guess, really.
> Although at the time I think most physicist understood that QM is "The Physics",
> many outsiders had the misunderstanding that it is the "Physics Of The Very Small".
> Well... honestly because thats how it was being described to them.
> But QM is "The Physics", and tests of the correspondence principle such as this one,
> along with many others before and since have shown that it is "The Physics".
> Well.. at least until you mention General Relativity.
> We may yet find that QM is "The Physics".

## [TABLE OF CONTENTS](CONTENTS.md)

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">
<img alt="Creative Commons License" style="border-width:0"
src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>
<br />
<span xmlns:dct="http://purl.org/dc/terms/"
href="http://purl.org/dc/dcmitype/Text" property="dct:title"
rel="dct:type">
The Optimum Distribution Of Energy Eigen-States For The Simple Harmonic Oscillator</span>
by <a xmlns:cc="http://creativecommons.org/ns#"
href="https://github.com/carlosjhr64/thesis" property="cc:attributionName"
rel="cc:attributionURL">carlosjhr64</a>
is licensed under a <a rel="license"
href="http://creativecommons.org/licenses/by/4.0/">
Creative Commons Attribution 4.0 International License</a>.

...but you should probably wait until I've corrected all the errors in this monstrosity!
