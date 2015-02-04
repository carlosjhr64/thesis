### [TABLE OF CONTENTS](CONTENTS.md)

## C. Proof: Necessary and Sufficient Conditions for Optimum Solution to the Programing Problem

The following is a summary.
Please see Kuhn and Tucker's "Nonlinear Programming" paper for a complete discussion.

     THEOREM:

       GIVEN:
         Fx = b - Ax
         Q[x,y] = g[x] + yFx
         xᵒ is a solution to the programming problem
           max g[x]
           sub Fx ≥ u
                x ≥ 0

`Q` is the Lagrangian function of the programming problem.
`g[x]` is the objective function to be maximize.
`Fx≥0` is the set of constraits on the set of decision variables `x`.

> So there's a claim that `xᵒ` maximizes `g[x]`,
> that `g[xᵒ]≥g[x]` for any allowed choice of x.

     The above is true IF AND ONLY IF:
       There exists a yᵒ such that
         (1): Dx Q[xᵒ,yᵒ] ≤ 0, Dx Q[xᵒ,yᵒ]xᵒ = 0, xᵒ ≥ 0
         (2): Dy Q[xᵒ,yᵒ] ≥ 0, yᵒ Dy Q[xᵒ,yᵒ] = 0, yᵒ ≥ 0

where say `Dq f[qᵒ]` is the gradient of `f[q]` with respect to `q` evaluated a `qᵒ`
for some function `f` of variable `q`.

The optimum sets `xᵒ` and `yᵒ` gives the saddle point of the Lagrangian function.
If the programming problem is linear,
the above condition give the well known duality theorem.[²](REFERENCE.md)

     PROOF:
       The GIVEN implies that
       Dx g[xᵒ] dx ≤ 0   for all dx such that
         Dx Fᵒ dx ≥ 0 and
         dx ≥ 0

That is, if g[xᵒ] is the best one can do,
any allowed deviation from xᵒ decreases the value of `g[x]`.

By a fundamental property of homogeneous linear inequalities,
there exists non-negative yᵒ and dᵒ such that[ⁱ](REFERNECE.md)

     -Dx g = yᵒ Dx Fᵒ + dᵒ,

Hence

     Dx Q[x,yᵒ] = Dx g[x] + yᵒ Dx Fᵒ
                ≤ Dx g[x] + yᵒ Dx Fᵒ + dᵒ = 0

Realizing that `dᵒxᵒ=0`, one obtains

     Dx Q[xᵒ,yᵒ] xᵒ  =  Dx g[xᵒ] xᵒ  +  yᵒ Dx Fᵒ xᵒ  =  0

Thus (1) is proved. For condition (2),

     Dy Q[xᵒ,yᵒ] = Dy F xᵒ ≥ 0
     yᵒ F xᵒ = 0

     END OF PROOF

> I was hoping reading this would make appendix B clearer to me, but no.
> So I'll proceed to section 7 and hope it all comes toguether for me somehow.
> Looks like my past self is failing to explain to myself what I apparently once knew.
> My guess is that I'm about to evaluate ΔpΔx with the Poisson distribution, but
> I don't see how I'm demonstrating KKT.
>
> I found this video on YouTube very helpful: [A Lagrange Multiplier Example](https://youtu.be/H4HN4ZrVm0w).
> I think I just need to add an addedum showing explicitly what I did.
> If I were to do a rewrite, I think I'd do a lot of restructuring of how I present things.
