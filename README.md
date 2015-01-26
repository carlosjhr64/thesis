# THE OPTIMUM DISTRIBUTION OF ENERGY EIGEN-STATES FOR THE SIMPLE HARMONIC OSCILLATOR
## A case study of a quadratic programming problem of infinite size.
### By Carlos J. Hernandez
### UCSC Senior Thesis, Spring 1990
### Revised 2015

> There is no point in me taking the time to copy my college thesis here verbatim.
> I've kept my notes from my thesis and thought I might enjoy rewritting,
> making clearer if possible, and adding points I did not have time to put on the final submission.
> Also, there are some interesting scribles sprinkle throughtout my notes,
> digressions I'll include for fun.  Let's start with this one:
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

## ABSTRACT

A single energy eigen-state of the simple harmonic oscillator
leaves a particle uncertain in its position and momentum.
Here I minimize this uncertainty through a distribution of energy eigen-states.
I show that a Poisson distribution of energy eigen-states is a feasible solution because
it satisfies the constraints for a physically meaningful distribution, and that
it is the optimum solution because
it satisfies the necessary and sufficient conditions for a minimum in the uncertainty
in the particle's position and momentum.

> Talking about my thesis to others since,
> I've come up against misunderstandings from laypeople.
> One misunderstanding has been that I was violating the uncertainty principle.
> Quantum Mechanics(QM) does not say you can't minimize uncertainties.
> It does put a lower bound ΔxΔp≥h, above zero.
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
