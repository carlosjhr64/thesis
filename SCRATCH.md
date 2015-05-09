[CONTENTS](CONTENTS.md)

# The (Over The Top (Extreme)) Full Monty
Here I write explicitly all my work.
In books you'll see `sin²(x)` to mean `sin(x)×sin(x)`.
I'll use that convention in general.
`𝓊²(𝓋)` will mean `𝓊(𝓋)×𝓊(𝓋)` and not `𝓊(𝓊(𝓋))`.
The initial part of this section goes over elementary material, but
it's a good warm-up and demonstrates my notation.

> This section was not in the original thesis.
> I'm using a proof checker using ruby-vim, which I'll publish(TODO).
> Eventually I hope to have the entire work in one stream of mathematical code.
> Please use GitHub's [issues](https://github.com/carlosjhr64/thesis/issues)
> to let me know of any errors (of any type).

<!-- TOC START -->
### Sections
<font size="+1">

 • [Expressions](#G0p) • [Conventions](#YEr) • [Bootstrapping](#6NE)
 • [𝒞 𝒶,𝒷](#0um) • [𝒫 𝒸,𝒹,ℯ,𝒻](#Cej) • [𝒲 𝓊,𝓋,𝓌,𝓍,𝓎,𝓏](#SNo) • [ℬ ℊ,𝒽](#Lr4)
 • [𝒮 𝓈,𝓉](#2gK) • [ℐ 𝓀,𝓁](#3RW) • [𝒬 𝒾,𝒿](#pIs) • [ₛ ₙ,ₘ,₀,₁,₂,₃,₍,₎,₊,₋](#SS5)
 • [𝒶; 𝒶 ⇒ 𝒷 ⇒ 𝒷](#gAu) • [=](#T2q) • [Synonym](#DCx) • [Groupings](#9PI)
 • [∈](#xSV) • [++,⋯](#wJ6) • [ℕ](#9ET) • [l,m,n,M,N](#ObZ) • [𝔑 𝔫](#fNd)
 • [𝔐 𝔪](#zpB) • [𝔇 𝔡](#6KL) • [Induction](#sOi) • [&#91;m,n&#93;](#EeZ)
 • [𝓊{𝓈|𝓍(𝓈)}](#H6V) • [Σ,+](#Pbn) • [𝓊+0](#Xi7) • [(𝔫+𝔩)++ = 𝔫+(𝔩)++](#uXU)
 • [𝓊+𝓋 = 𝓋+𝓊](#P9m) • [𝓊|𝓍+𝓌|𝓎 = 𝓊+𝓌](#nvp) • [Σ&#91;l,m&#93;{l|𝓊(n)}](#Ifk)
 • [Σₙ,𝓊ₙ](#U7Q) • [×](#zcN) • [-](#fAs) • [/](#XIb) • [ℤ](#r5l)
 • [ℨ 𝔦,𝔧,𝔨](#22g) • [ℚ](#mgl) • [ⁿ,ᵐ](#ubG) • [ₙ,ₘ](#SB5) • [Precedence rules](#MIM)
 • [uᵥ](#frL) • [𝓊{𝓋ₙ}](#4bK) • [Σ&#91;l,k&#93;{j|uⱼ}](#zJL) • [n×u](#vkP)
 • [×⋯](#uyg) • [Σuₙ](#kJ6) • [Σₙuₙ](#MlN) • [∞](#9XA) • [∑](#zQw)
 • [⋅](#Jt7) • [{⋯}⋅{⋯}](#IK3) • [∑ₗ](#tky) • [Π](#J5V) • [uᵛ](#y3Z)
 • [√u](#8wf) • [|u|](#fxq) • [↓,↑](#3r3) • [↧,↥](#1U2) • [Σu↑](#U10)
 • [∑u↑](#Uf9) • [∑u↓](#blg) • [𝐿](#vGe) • [uₒ≡Σuₙ](#CuZ) • [ℝ](#yfS)
 • [x,t](#pZX) • [∞/∞](#iyp) • [𝜖≡a/∞](#rNP) • [Σrⁿ](#5qT) • [⅀](#s2N)
 • [⨋ₓ](#SuG) • [ℂ](#Ama) • [ℯ](#NLb) • [Sine](#ZE8) • [Cosine](#CgT)
 • [𝑖](#FU8) • [&#42;](#XXd) • [𝒟ₓ](#FD0) • [𝒟(u⋅v)=𝒟u⋅v+u⋅𝒟v](#9Ql)
 • [∫](#iPk) • [n!](#zaX) • [(ⁿₘ)](#qsc) • [nₘ](#t99) • [0ₘ](#KLm)
 • [1ₘ](#ngq) • [2ₘ](#eUd) • [3ₘ](#pOG) • [nₘ=(n+m)!/n!](#vOj)
 • [n₋ₘ=(n-m)!/n!](#w4y) • [n₋ₙ=1/n!](#6OO) • [(ⁿₘ)=m-ₘ/n-ₘ](#SoK)
 • [n↥,n₀,n↧](#I4Q) • [nᵥn!](#jL9) • [ŉ](#44r) • [ʼu](#Yv1) • [u↑ˡᵥ](#4H1)
 • [𝔩](#wNn) • [S²+C²=1](#IwS) • [ℯⁱᵘ=Cᵤ+𝑖Sᵤ](#VkX) • [𝛿](#VuP)
 • [⧼v⧽](#nXb) • [Δ²](#2ef) • [𝑃](#Uz0) • [𝑝](#2on) • [𝒫](#IRG)
 • [𝒫↑↓≠𝒫↓↑](#ZMc) • [𝛿𝒫↑↓=𝛿𝒫↓↑&#42;](#DZ0) • [κ,μ](#y3s) • [π](#vmD)
 • [½!](#SB2) • [ℏ](#1Xb) • [ω](#Jji) • [f](#0h7) • [Eₙ](#2Xh)
 • [𝐱](#0bH) • [𝐩](#w6M) • [Δ²𝐩](#mo3) • [Δ²𝐱](#8SV) • [&#91;𝐱,𝐩&#93;](#bST)
 • [𝐇](#bdY) • [⌽ᵗₙ](#WEu) • [𝕌{⌽}](#fzU) • [⌽→φ](#h8y) • [sₙ,cₙ](#zlN)
 • [ñ](#Ojo) • [Eₒ](#k5Y) • [ñ²=𝐿Σ{n(n-1)𝑃ₙ}](#LJ7) • [p→𝑃](#mI6)
 • [ξ](#Pvg) • [⨋](#AXS) • [𝒟](#8P4) • [𝛽](#FnP) • [𝒽](#hIf) • [𝒟ₓξ](#QcB)
 • [𝒟 x](#o8p) • [𝐴ₙ](#yYZ) • [𝒢,ℊ](#lQl) • [ℋ](#m3i) • [𝒟ℋ](#mV6)
 • [ℋ↑](#oNs) • [ξℋ](#fqa) • [Ψₙ](#rrF) • [𝒟 Ψ](#W3A) • [𝑝𝒟 Ψ](#e2c)
 • [Ψₒ](#lHR) • [ñ²=Σ{n²ΨₙΨₙ}](#quL) • [ξΨ](#4V4) • [⧼ξ₀⧽](#1Wx)
 • [⌽𝐴ℋ↓/½n↓=⌽↥/√½n↓⌽↓Ψ↓](#jiD) • [⌽𝐴ℋ↑=⌽↧√2n↑⌽↑Ψ↑](#5Mz) • [𝑝↑𝑝=√&#91;ñ/n↑&#93;𝑃](#V1C)
 • [𝑝↓𝑝=𝑃/√&#91;n↓ñ&#93;](#AyD) • [⧼ξₜ⧽](#geS) • [⧼ξ²⧽](#WaV)
 • [Δ²ξ](#8NW) • [Optimization problem](#1Pu) • [symmetries?](#i9c)
 • [ℒ](#ij2) • [𝒟 ⧼n⧽=0](#Jbc) • [𝒟ₓ⧼𝐱²⧽](#iFR) • [⧼u⧽ₜ](#3nH)
 • [Ψₒₜ](#y2B) • [⌽↑](#p3u) • [⌽↓](#BNu) • [⌽↑,⌽↓](#2q7) • [𝛿↓](#g9G)
 • [𝛿↑](#QlY) • [⧼𝐱⧽](#Nde) • [⧼𝐱⧽²](#1o3) • [⧼ξ⧽](#GJG) • [⧼𝐱²⧽](#B0z)
 • [⧼𝐱²⧽-⧼𝐱⧽²](#9QN) • [⧼𝐱⧽ₜ](#I9g) • [⧼𝐩⧽](#eVh) • [⧼𝐩⧽²](#8BU)
 • [⧼𝐩²⧽](#TRj) • [⧼𝐩²⧽-⧼𝐩⧽²](#7HF) • [(⧼𝐱²⧽-⧼𝐱⧽²)(⧼𝐩²⧽-⧼𝐩⧽²)](#zcf)
 • [Resources](#2Nz) •


</font>
<!-- TOC END -->

###<a name="G0p"></a> Expressions
This file is written in [Markdown](http://en.wikipedia.org/wiki/Markdown) format.
Proper mathematical
[expressions](http://en.wikipedia.org/wiki/Expression_%28mathematics%29)
will start with four spaces and end with either a newline or a pound sign, #.
Everything else is commentary.

###<a name="YEr"></a> Conventions

> TODO:
> Rules for expression than end with = and → which then
> continue on the next line are emerging, but
> I haven't yet decided exactly what they are.

> TODO:
> Convention on alphabet/letter use?
> `π` is a constant `ℝ < ℂ`.
> `𝑖` is a constant `𝕀 < ℂ`?
> `n` is variable `ℕ < ℤ < ℚ < ℝ < ℂ`.
> `N` is a constant `ℕ`.
> :-??

* 𝒜 Normal calligraphy letters are general patterns.
* 𝔄 Normal fraktur letters are specific patterns.
* 𝔸 Double struck letters are sets.

###<a name="6NE"></a> Bootstrapping
When writting my proofchecker,
I tried to assume as little as possible about the notation, but
the symbols `;⇒=(){}[]⸨⸩<:!⊢#` have predefined meaning in my proofchecker
which may depend on context.

In a statement `;⇒#=` are to be considered reserved words.
`; ` separates statements in a compound statement.
` ⇒ ` separates statements of a map creating an "if-then" statement.
`#` marks the end of a statement, and the start of a comment.

The proochecker assumes `=` is used in the usual way, and
as some support for its use.

The proofchecker assumes `(){}[]⸨⸩` need to be balanced in the conventional way, and
will check for that.

The `<:!⊢` symbols have meaning in context.
A statement ending in `⊢` is accepted as true.
When it ends in ` ⊢⊢`, it is marked as a Theorem, T.
When it ends in ` ⊢`, it is marked as an Axiom, A.
Axioms are not allowed to redefine terms.
When it ends in ` :⊢`, it is marked as a Definition, D.
Definitions are allowed to redefine a term as a undefined term.
Statements ending in ` !⊢` are declarations, instructions to the proofchecker.
Statements ending in ` <⊢` are statements previously stated.

> OK, here we go!

###<a name="0um"></a> 𝒞 𝒶,𝒷
Clause:

    𝒞 /[^\s⇒;][^⇒;]*[^\s⇒;]|[^\s⇒;]/ !⊢
    𝒞 { 𝒶,𝒷 }                        !⊢

###<a name="Cej"></a> 𝒫 𝒸,𝒹,ℯ,𝒻
Phrase(not greedy, may be zero length):

    𝒫 /[^⇒=;\s][^⇒=;]*?[^⇒=;\s]|[^⇒=;\s]?/ !⊢
    𝒫 { 𝒸,𝒹,ℯ,𝒻 }                          !⊢

###<a name="SNo"></a> 𝒲 𝓊,𝓋,𝓌,𝓍,𝓎,𝓏
Word:

    𝒲 /\([^()]+\)|:?[\p{L}\p{N}]+/ !⊢
    𝒲 { 𝓊,𝓋,𝓌,𝓍,𝓎,𝓏 }              !⊢

###<a name="Lr4"></a> ℬ ℊ,𝒽
Word Boundary:

    #ℬ /\b|[, |(+){-}|\[\]]/ !⊢
    ℬ /\b|[,(){}+|]/ !⊢
    ℬ { ℊ,𝒽 }        !⊢

###<a name="2gK"></a> 𝒮 𝓈,𝓉
Set Group(not greedy, may be zero length):

    𝒮 /[^{}|]*?/ !⊢
    𝒮 { 𝓈,𝓉 }    !⊢

###<a name="3RW"></a> ℐ 𝓀,𝓁
Interval Group(not greedy, may be zero length):

    ℐ /[^\[\]|]*?/ !⊢
    ℐ { 𝓀,𝓁 }      !⊢

###<a name="pIs"></a> 𝒬 𝒾,𝒿
Sequence Group(not greedy, may be zero length):

    𝒬 /[^()]*?/ !⊢
    𝒬 { 𝒾,𝒿 }   !⊢

###<a name="SS5"></a> ₛ ₙ,ₘ,₀,₁,₂,₃,₍,₎,₊,₋
Subscripts:

    ₛ /[ₙₘ₀₁₂₃₄₅₆₇₈₉₍₎₊₋]+/ !⊢
    ₛ { ᵤ,ᵥ }               !⊢

###<a name="gAu"></a> 𝒶; 𝒶 ⇒ 𝒷 ⇒ 𝒷
[Modus Ponem](http://en.wikipedia.org/wiki/Modus+Ponen):

    𝒶; 𝒶 ⇒ 𝒷 ⇒ 𝒷  ⊢#A1 Modus Ponem.

###<a name="T2q"></a> =
[Equality](http://en.wikipedia.org/wiki/Equality_&#40;mathematics&#41;):

    𝒸 = 𝒹 ⇒ 𝒸 ⇒ 𝒹  ⊢#A2 Equivalent Statement.

    𝒸 = 𝒸                  ⊢#A3 Reflexive.
    𝒸 = 𝒹 ⇒ 𝒹 = 𝒸          ⊢#A4 Symmetric.
    𝒸 = 𝒹; 𝒹 = ℯ ⇒ 𝒸 = ℯ   ⊢#A5 F-Transitive.
    𝒸 = 𝒹 ⇒ ℯ = 𝒸 ⇒ ℯ = 𝒹  ⊢#A6 B-Transitive.

###<a name="DCx"></a> Synonym

The following are my assumptions of the language, and
I don't know an authoritive reference to justify them.
It does need to be words though, not phrases.

    𝓊 = 𝓋 ⇒ 𝓊𝓎 = 𝓋𝓎    ⊢#A7 Left Synonym.
    𝓊 = 𝓋 ⇒ 𝓍𝓊 = 𝓍𝓋    ⊢#A8 Right Synonym.
    𝓊 = 𝓋 ⇒ 𝓍𝓊𝓎 = 𝓍𝓋𝓎  ⊢#A9 Context Synonym.

With phrases, the synonyms need to be semantically bounded.

    𝒸 = 𝒹 ⇒ 𝒸𝒽𝒻 = 𝒹𝒽𝒻       #P10 Left Bounded Synonym ∵ A7 Left Synonym.
    𝒸 = 𝒹 ⇒ ℯℊ𝒸 = ℯℊ𝒹       #P11 Right Bounded Synonym ∵ A8 Right Synonym.
    𝒸 = 𝒹 ⇒ ℯℊ𝒸𝒽𝒻 = ℯℊ𝒹𝒽𝒻   #P12 Bounded Context Synonym ∵ A9 Context Synonym.

###<a name="9PI"></a> Groupings

    𝓈𝒽𝒹 = (𝓈)𝒽𝒹  ⊢#A13 Left Grouping.
    (𝓈)𝒽𝒹 = 𝓈𝒽𝒹   #M14 Left Ungrouping ∵ A4,A13 Symmetric.

    𝒸ℊ𝓈 = 𝒸ℊ(𝓈)  ⊢#A15 Right Grouping.
    𝒸ℊ(𝓈) = 𝒸ℊ𝓈   #M16 Right Ungrouping ∵ A4,A15 Symmetric.

    𝒸ℊ𝓈𝒽𝒹 = 𝒸ℊ(𝓈)𝒽𝒹  ⊢#A17 Context Grouping.
    𝒸ℊ(𝓈)𝒽𝒹 = 𝒸ℊ𝓈𝒽𝒹   #M18 Context Ungrouping ∵ A4,A17 Symmetric.

###<a name="xSV"></a> ∈
[Element](http://en.wikipedia.org/wiki/Element_&#40;mathematics&#41;) operator:

    𝓊 = {𝓈} ⇒ 𝓊{𝓈}  ⊢#A19 Set Contains Elements.
    𝓊{𝓈𝓋𝓉} ⇒ 𝓊{𝓋}   ⊢#A20 Element Contained By Set.
    𝓋∈𝓊 = 𝓊{𝓋}      ⊢#A21 Contained By Means Element Of.
    𝓊{𝓋} = 𝓋∈𝓊       #M22 ∵ A4,A21 Symmetric.
    𝓊{𝓋} ⇒ 𝓋∈𝓊       #M23 If Contained By, Element Of ∵ A2,M22 Equivalent Statement.
    𝓋∈𝓊 ⇒ 𝓊{𝓋}       #M24 If Element Of, Contained By ∵ A2,A21 Equivalent Statement.

###<a name="wJ6"></a> ++,⋯
Successor operator and
[Ellipsis](http://en.wikipedia.org/wiki/Ellipsis#In_mathematical_notation):

    {𝓈𝓊,𝓋𝓉} ⇒ 𝓋 = 𝓊++ ⊢#A25 Successor.
    {𝓈𝓊,𝓋𝓉} ⇒ 𝓊 = 𝓋-- ⊢#A26 Preccessor.

    𝒸ℊ𝓊,⋯𝒹 = 𝒸ℊ𝓊,𝓊++,⋯𝒹  ⊢#A27 Successor Ellipsis.
    𝒸ℊ𝓊,⋯,𝓊𝒹 = 𝒸ℊ𝓊𝒹      ⊢#A28 Terminal Ellipsis.

    𝒸ℊ𝓊(𝓋),⋯𝒹 = 𝒸ℊ𝓊(𝓋),𝓊(𝓋++),⋯𝒹  ⊢#A29 Sequence Successor Ellipsis.
    𝒸ℊ𝓊(𝓋),⋯,𝓊(𝓋)𝒹 = 𝒸ℊ𝓊(𝓋)𝒹      ⊢#A30 Terminal Sequence Ellipsis.

    𝒸ℊ𝓊ᵥ,⋯𝒹 = 𝒸ℊ𝓊ᵥ,𝓊ᵥ₊₁,⋯𝒹  ⊢#A31 Sequence Successor Ellipsis.
    𝒸ℊ𝓊ᵥ,⋯,𝓊ᵥ𝒹 = 𝒸ℊ𝓊ᵥ𝒹      ⊢#A32 Terminal Sequence Ellipsis.

    𝒸ℊ𝓊(𝓋)+⋯𝒹 = 𝒸ℊ𝓊(𝓋)+𝓊(𝓋++)+⋯𝒹  ⊢#A33 Series Successor Ellipsis.
    𝒸ℊ𝓊(𝓋)+⋯+𝓌(𝓋)𝒹 = 𝒸ℊ𝓌(𝓋)𝒹      ⊢#A34 Terminal Series Ellipsis.

    𝒸ℊ𝓊ᵥ+⋯𝒹 = 𝒸ℊ𝓊ᵥ+𝓊ᵥ₊₁+⋯𝒹  ⊢#A35 Series Successor Ellipsis.
    𝒸ℊ𝓊ᵥ+⋯+𝓌ᵥ𝒹 = 𝒸ℊ𝓌ᵥ𝒹      ⊢#A36 Terminal Series Ellipsis.

    𝒸ℊ𝓊|𝓋+⋯𝒹 = 𝒸ℊ𝓊|𝓋+𝓊|(𝓋++)+⋯𝒹  ⊢#A37 Series Successor Ellipsis.
    𝒸ℊ𝓊|𝓋+⋯+𝓌|𝓋𝒹 = 𝒸ℊ𝓌|𝓋𝒹        ⊢#A38 Terminal Series Ellipsis.

###<a name="9ET"></a> ℕ
[Natural (Counting) numbers](http://en.wikipedia.org/wiki/Natural_number):

    ℕ = {0,1,⋯}  ⊢#A39 Natural Numbers.
    ℕ            ⊢#A40 Numbers Exist.

    ℕ ⇒ {0,1,⋯}      #M41 ∵ A2,A39 Equivalent Statement.
    ℕ; ℕ ⇒ {0,1,⋯}   #C42 ∵ A40,M41 Numbers Exist.
    {0,1,⋯}          #M43 ∵ A1,C42 Modus Ponem.

I need to say that `{0,1,⋯}` is true in order to say that `1` is the successor of `0`.
Simply that `ℕ = {0,1,⋯}` does not say either is true.
I might have avoided the issue had Elipsis beed defined within `𝒞` instead of `𝒫`, but
I think sematically as it is works just fine.
There after, we're just giving each successor element a name:

    1 = 0++   #M44 ∵ A25,M43 Successor.
    2 = 1++  ⊢#A45.
    3 = 2++  ⊢#A46.
    4 = 3++  ⊢#A47.
    5 = 4++  ⊢#A48.
    6 = 5++  ⊢#A49.
    7 = 6++  ⊢#A50.
    8 = 7++  ⊢#A51.
    9 = 8++  ⊢#A52.

    0++ = 1   #M53 ∵ A4,M44 Symmetric.
    1++ = 2   #M54 ∵ A4,A45 Symmetric.
    2++ = 3   #M55 ∵ A4,A46 Symmetric.
    3++ = 4   #M56 ∵ A4,A47 Symmetric.
    4++ = 5   #M57 ∵ A4,A48 Symmetric.
    5++ = 6   #M58 ∵ A4,A49 Symmetric.
    6++ = 7   #M59 ∵ A4,A50 Symmetric.
    7++ = 8   #M60 ∵ A4,A51 Symmetric.
    8++ = 9   #M61 ∵ A4,A52 Symmetric.

    # Prove: ℕ = {0,1,2,⋯}.
    {0,1,⋯} = {0,1,1++,⋯}                    #P62 ∵ A27 Successor Ellipsis.
    ℕ = {0,1,⋯}; {0,1,⋯} = {0,1,1++,⋯}       #C63 ∵ A39,P62 Natural Numbers.
    ℕ = {0,1,1++,⋯}                          #M64 ∵ A5,C63 F-Transitive.
    {0,1,1++,⋯} = {0,1,2,⋯}                  #M65 ∵ P12,M54 Bounded Context Synonym.
    ℕ = {0,1,1++,⋯}; {0,1,1++,⋯} = {0,1,2,⋯} #C66 ∵ M64,M65.
    ℕ = {0,1,2,⋯}                            #M67 ∵ A5,C66 F-Transitive.
    #

    # Prove: ℕ = {0,1,2,3,⋯}.
    {0,1,2,⋯} = {0,1,2,2++,⋯}   #P68 ∵ A27 Successor Ellipsis.
    {0,1,2,2++,⋯} = {0,1,2,3,⋯} #M69 ∵ P12,M55 Bounded Context Synonym.
    ℕ = {0,1,2,3,⋯}             #E70 ∵ A39 Natural Numbers.
    #

    # And so on, I can show...
    ℕ = {0,1,2,3,4,5,6,7,8,9,⋯} ⊢⊢#T71 Digits.
    #

###<a name="ObZ"></a> l,m,n,M,N

    ℕ{l,m,n,o,M,N} ⊢#A72 Number Variables.
    ℕ{N}            #M73 ∵ A20,A72 Element Contained By Set.
    N∈ℕ             #M74 ∵ M23,M73 If Contained By, Element Of.

    # This just simplifies notation later on.
    M++ = N  ⊢#A75 N Succeeds M.
    N = M++   #M76 N Succeds M ∵ A4,A75 Symmetric.

###<a name="fNd"></a> 𝔑 𝔫

    𝔑 /\d+|[lmnMN]/ !⊢
    𝔑 { 𝔩,𝔫 }       !⊢

    ℕ{𝔩,𝔫} ⊢#A77.
    ℕ{𝔩}    #M78 ∵ A20,A77 Element Contained By Set.
    ℕ{𝔫}    #M79 ∵ A20,A77 Element Contained By Set.

###<a name="zpB"></a> 𝔐 𝔪

    𝔐 /[lmn]/ !⊢
    𝔐 { 𝔪,𝔬 } !⊢

    ℕ{𝔪,𝔬} ⊢#A80.
    ℕ{𝔪}    #M81 ∵ A20,A80 Element Contained By Set.
    ℕ{𝔬}    #M82 ∵ A20,A80 Element Contained By Set.

###<a name="6KL"></a> 𝔇 𝔡

    𝔇 /\d+/   !⊢
    𝔇 { 𝔡,𝔢 } !⊢

    ℕ{𝔡,𝔢} ⊢#A83.
    ℕ{𝔡}    #M84 ∵ A20,A83 Element Contained By Set.
    ℕ{𝔢}    #M85 ∵ A20,A83 Element Contained By Set.

###<a name="sOi"></a> Induction
Step by step, I can always reach step 𝔫:

    𝓊(0) = 𝓊(1); 𝓊(𝔪) = 𝓊(𝔪+1) ⇒ 𝓊(0) = 𝓊(𝔫)  ⊢#A86 Induction.

###<a name="EeZ"></a> [m,n]

    [𝓊,𝓋] = {𝓊,⋯,𝓋}  ⊢#A87 Interval.

    # Prove: [0,3] = {1,2,3}.
    [0,3] = {0,⋯,3}    #P88 ∵ A87 Interval.
    = {0,0++,⋯,3}      #P89 ∵ A27 Successor Ellipsis.
    = {0,1,⋯,3}        #M90 ∵ P12,M53 Bounded Context Synonym.
    = {0,1,1++,⋯,3}    #P91 ∵ A27 Successor Ellipsis.
    = {0,1,2,⋯,3}      #M92 ∵ P12,M54 Bounded Context Synonym.
    = {0,1,2,2++,⋯,3}  #P93 ∵ A27 Successor Ellipsis.
    = {0,1,2,3,⋯,3}    #M94 ∵ P12,M55 Bounded Context Synonym.
    = {0,1,2,3}        #P95 ∵ A28 Terminal Ellipsis.
    [0,3] = {0,1,2,3}  #E96 ∵ P88.
    #

###<a name="H6V"></a> 𝓊{𝓈|𝓍(𝓈)}

    𝓊 = 𝓋{𝓈|𝓉} ⇒ 𝓊{𝓉}    ⊢#A97 Iterators are sets.
    𝓋{𝓈|𝓉} ⇒ 𝓋{𝓈}        ⊢#A98 Iterators map sets.
    ℕ{n|𝓍(n)} = (𝓍(0),⋯) ⊢#A99 Sequence.

    𝓏 = ℕ{𝓍|𝓎(𝓍)} ⇒ 𝓏{𝓎(𝓍)} #P100 ∵ A97 Iterators are sets.
    ℕ{𝓍|𝓎(𝓍)} ⇒ ℕ{𝓍}        #P101 ∵ A98 Iterators map sets.

    # Prove: ℕ{n|𝓍(n)} = (𝓍(0),𝓍(1),⋯).
    (𝓍(0),⋯) = (𝓍(0),𝓍(0++),⋯)  #P102 ∵ A29 Sequence Successor Ellipsis.
    = (𝓍(0),𝓍(1),⋯)             #M103 ∵ P12,M53 Bounded Context Synonym.
    ℕ{n|𝓍(n)} = (𝓍(0),𝓍(1),⋯)   #E104 ∵ A99 Sequence.
    #

###<a name="Pbn"></a> Σ,+
[Addition](http://en.wikipedia.org/wiki/Addition):

    Σ(𝓊,𝓋) = 𝓊+𝓋         ⊢#A105 Addition.
    ℕ{𝓊} ⇒ 𝓊++ = Σ(𝓊,1)  ⊢#A106 Number Successor By Addition.
    Σ(𝓊,1) = 𝓊+1          #P107 ∵ A105 Addition.

    ℕ{𝔫} ⇒ 𝔫++ = Σ(𝔫,1)       #P108 ∵ A106 Number Successor By Addition.
    ℕ{𝔫}; ℕ{𝔫} ⇒ 𝔫++ = Σ(𝔫,1) #C109 ∵ M79,P108.
    𝔫++ = Σ(𝔫,1)              #M110 ∵ A1,C109 Modus Ponem.
    Σ(𝔫,1) = 𝔫+1              #P111 ∵ A105 Addition.
    𝔫++ = 𝔫+1                 #E112 ∵ M110.
    𝔫+1 = 𝔫++                 #M113 ∵ A4,E112 Symmetric.

    M++ = M+1   #P114 ∵ E112.
    M+1 = M++   #P115 ∵ M113.

    M+1 = N   #E116 ∵ A75 N Succeeds M.
    N = M+1   #M117 ∵ A4,E116 Symmetric.

    n++ = n+1   #P118 ∵ E112.
    n+1 = n++   #P119 ∵ M113.

    m++ = m+1   #P120 ∵ E112.
    m+1 = m++   #P121 ∵ M113.

    # Prove: 0+1 = 1.
    0+1 = 0++          #P122 ∵ M113.
    0+1 = 0++; 0++ = 1 #C123 ∵ P122,M53.
    0+1 = 1            #M124 ∵ A5,C123 F-Transitive.
    #

    # Prove: 1+1 = 2.
    1+1 = 1++ #P125 ∵ M113.
    1+1 = 2   #E126 ∵ A45.
    #

    # Prove: 2+1 = 3.
    2+1 = 2++ #P127 ∵ M113.
    2+1 = 3   #E128 ∵ A46.
    #

    # And so on, I can show:
    3+1 = 4 :⊢#D129.
    4+1 = 5 :⊢#D130.
    5+1 = 6 :⊢#D131.
    6+1 = 7 :⊢#D132.
    7+1 = 8 :⊢#D133.
    8+1 = 9 :⊢#D134.

    # Prove: 1+1+1 = 3.
    1+1+1 = 2+1 #M135 ∵ P10,E126 Left Bounded Synonym.
    1+1+1 = 3   #E136 ∵ A46.
    #

    # Prove: 1+1+1+1 = 4.
    1+1+1+1 = 3+1 #M137 ∵ P10,E136 Left Bounded Synonym.
    1+1+1+1 = 4   #E138 ∵ A47.
    #

    # And so on, I can show:
    1+1+1+1+1 = 5         :⊢#D139.
    1+1+1+1+1+1 = 6       :⊢#D140.
    1+1+1+1+1+1+1 = 7     :⊢#D141.
    1+1+1+1+1+1+1+1 = 8   :⊢#D142.
    1+1+1+1+1+1+1+1+1 = 9 :⊢#D143.

    # Prove: 2+3 = 5.
    5 = 1+1+1+1+1 #M144 ∵ A4,D139 Symmetric.
    = 2+1+1+1     #M145 ∵ P10,E126 Left Bounded Synonym.
    = 2+3         #M146 ∵ P11,E136 Right Bounded Synonym.
    2+3 = 5       #E147 ∵ A48.
    #

    # Prove: 3+2 = 5.
    5 = 1+1+1+1+1 <⊢#M144 ∵ A4,D139 Symmetric.
    = 3+1+1         #M148 ∵ P10,E136 Left Bounded Synonym.
    = 3+2           #M149 ∵ P11,E126 Right Bounded Synonym.
    3+2 = 5         #E150 ∵ A48.
    #

    # Prove: 3+2 = 2+3.
    3+2 = 5  <⊢#E150 ∵ A48.
    = 2+3      #M151 ∵ A4,E147 Symmetric.
    3+2 = 2+3  #E152 ∵ A48.
    #

###<a name="Xi7"></a> 𝓊+0
Zero will always be an identity object to addition:

    𝓊+0 = 𝓊  ⊢#A153 Additive Identity.
    0+𝓋 = 𝓋  ⊢#A154 Additive Identity.
    𝓊 = 𝓊+0   #M155 Additive Identity ∵ A4,A153 Symmetric.
    𝓋 = 0+𝓋   #M156 Additive Identity ∵ A4,A154 Symmetric.

###<a name="uXU"></a> (𝔫+𝔩)++ = 𝔫+(𝔩)++
Note that our notion of grouping is equivalent
to the succesor's axiom of grouping, so that here
the succesor's axiom of grouping is reflected in the notation.

    𝔫+𝔩++ = (𝔫+𝔩)++   #P157 ∵ A13 Left Grouping.
    𝔫+𝔩++ = 𝔫+(𝔩)++   #P158 ∵ A17 Context Grouping.
    (𝔫+𝔩)++ = 𝔫+(𝔩)++ #E159 Succesor Grouping ∵ P157.

So the above three line restated as numbers
expresed as the sum of ones:

    1+⋯+1+1+⋯+1++ = (1+⋯+1+1+⋯+1)++   #P160 ∵ A13 Left Grouping.
    1+⋯+1+1+⋯+1++ = 1+⋯+1+(1+⋯+1)++   #P161 ∵ A17 Context Grouping.
    (1+⋯+1+1+⋯+1)++ = 1+⋯+1+(1+⋯+1)++ #E162 ∵ P160.

And reinterpreting the successor and addition by one:

    1++ = 1+1                     #P163 ∵ E112.
    1+⋯+1+1+⋯+1++ = 1+⋯+1+1+⋯+1+1 #M164 ∵ P11,P163 Right Bounded Synonym.

    1+⋯+1+1+⋯+1+1 = (1+⋯+1+1+⋯+1)+1   #P165 ∵ A13 Left Grouping.
    1+⋯+1+1+⋯+1+1 = 1+⋯+1+(1+⋯+1)+1   #P166 ∵ A17 Context Grouping.
    (1+⋯+1+1+⋯+1)+1 = 1+⋯+1+(1+⋯+1)+1 #E167 ∵ P160.

###<a name="P9m"></a> 𝓊+𝓋 = 𝓋+𝓊
One can always expand out the sum of two number as the sum of ones,
and regroup to show the equivalent commuted expression.
> TOD0: show the formal proof.

I will only use the `+` operator when it commutes.

    𝓊+𝓋 = 𝓋+𝓊 ⊢⊢#T168 Commutative.
    m+n = n+m   #P169 ∵ T168 Commutative.

###<a name="nvp"></a> 𝓊|𝓍+𝓌|𝓎 = 𝓊+𝓌
Labeled Sum:

    𝓊|𝓍+𝓌|𝓎 = 𝓊+𝓌  ⊢#A170 Labeled Sum.
    𝓋|𝓍+𝓌 = 𝓋+𝓌    ⊢#A171 Labeled Sum.

###<a name="Ifk"></a> Σ[l,m]{l|𝓊(n)}

    # Main Definition:
    Σ[𝓍,𝓎]{𝓏|𝓊(𝓏)} = 𝓊(𝓍)+⋯+𝓊(𝓎) ⊢#A172 Series.

    # Comprehension Forms:
    Σ{𝓍|𝓊(𝓍)} = 𝓊(0)+⋯     ⊢#A173 Infinite Series.
    Σ[𝓍] = Σ[1,𝓍]          ⊢#A174 Series Starting At One.
    Σ[𝓍,𝓎]{|𝓊} = 𝓊|𝓍+⋯+𝓊|𝓎 ⊢#A175 Sum Of Labeled Variable.

    Σ[𝓍]{|𝓊} = Σ[1,𝓍]{|𝓊} #M176 ∵ P10,A174 Left Bounded Synonym.
    = 𝓊|1+⋯+𝓊|𝓍           #P177 ∵ A175 Sum Of Labeled Variable.
    Σ[𝓍]{|𝓊} = 𝓊|1+⋯+𝓊|𝓍  #E178 ∵ M176.

    # Prove: Σ{𝓍|𝓊(𝓍)} = 𝓊(0)+𝓊(1)+⋯.
    Σ{𝓍|𝓊(𝓍)} = 𝓊(0)+⋯    <⊢#A173 Infinite Series.
    = 𝓊(0)+𝓊(0++)+⋯         #P179 Infinite Series ∵ A33 Series Successor Ellipsis.
    = 𝓊(0)+𝓊(1)+⋯           #M180 ∵ P12,M53 Bounded Context Synonym.
    Σ{𝓍|𝓊(𝓍)} = 𝓊(0)+𝓊(1)+⋯ #E181 ∵ A173 Infinite Series.
    #

    # Prove: Σ[0,0]{n|𝓊(n)} = 𝓊(0).
    Σ[0,0]{n|𝓊(n)} = 𝓊(0)+⋯+𝓊(0) #P182 ∵ A172 Series.
    = 𝓊(0)                       #P183 ∵ A34 Terminal Series Ellipsis.
    Σ[0,0]{n|𝓊(n)} = 𝓊(0)        #E184 ∵ P182.
    #

    𝐔(𝒾) = 1 :⊢#D185.
    𝐔(0) = 1 #P186 ∵ D185.
    𝐔(1) = 1 #P187 ∵ D185.
    𝐔(2) = 1 #P188 ∵ D185.
    𝐔(3) = 1 #P189 ∵ D185.
    # ⋯
    𝐔(n+1) = 1 #P190 ∵ D185.
    𝐔(N) = 1   #P191 ∵ D185.

    # Prove: Σ[1,N]{n|𝐔(n)} = 1+𝐔(1++)+⋯+𝐔(N).
    Σ[1,N]{n|𝐔(n)} = 𝐔(1)+⋯+𝐔(N)     #P192 ∵ A172 Series.
    = 𝐔(1)+𝐔(1++)+⋯+𝐔(N)             #P193 ∵ A33 Series Successor Ellipsis.
    = 1+𝐔(1++)+⋯+𝐔(N)                #M194 ∵ P10,P187 Left Bounded Synonym.
    Σ[1,N]{n|𝐔(n)} = 1+𝐔(1++)+⋯+𝐔(N) #E195 ∵ P192.
    #

    𝐮(𝒾) = 𝒾+𝐔((𝒾)++)+⋯+𝐔(N) ⊢#A196.

    # Prove: 𝐮(0) = 𝐮(1).
    𝐮(0) = 0+𝐔((0)++)+⋯+𝐔(N) #P197 ∵ A196.
    = 0+𝐔(0++)+⋯+𝐔(N)        #P198 ∵ M18 Context Ungrouping.
    = 0+𝐔(1)+⋯+𝐔(N)          #M199 ∵ P12,M53 Bounded Context Synonym.
    = 0+𝐔(1)+𝐔(1++)+⋯+𝐔(N)   #P200 ∵ A33 Series Successor Ellipsis.
    = 0+1+𝐔(1++)+⋯+𝐔(N)      #M201 ∵ P11,M194 Right Bounded Synonym.
    = 1+𝐔(1++)+⋯+𝐔(N)        #M202 ∵ P10,M124 Left Bounded Synonym.
    = 1+𝐔((1)++)+⋯+𝐔(N)      #P203 ∵ A17 Context Grouping.
    𝐮(0) = 1+𝐔((1)++)+⋯+𝐔(N) #E204 ∵ P197.
    𝐮(1) = 1+𝐔((1)++)+⋯+𝐔(N) #P205 ∵ A196.
    𝐮(0) = 𝐮(1)              #E206 ∵ P197.
    #
    
    # Prove: 𝐮(n) = 𝐮(n+1).
    𝐮(n) = n+𝐔((n)++)+⋯+𝐔(N)       #P207 ∵ A196.
    = n+𝐔(n++)+⋯+𝐔(N)              #P208 ∵ M18 Context Ungrouping.
    = n+𝐔(n+1)+⋯+𝐔(N)              #M209 ∵ P12,P118 Bounded Context Synonym.
    = n+𝐔((n+1))+⋯+𝐔(N)            #P210 ∵ A17 Context Grouping.
    = n+𝐔((n+1))+𝐔((n+1)++)+⋯+𝐔(N) #P211 ∵ A33 Series Successor Ellipsis.
    = n+𝐔(n+1)+𝐔((n+1)++)+⋯+𝐔(N)   #P212 ∵ M18 Context Ungrouping.
    = n+1+𝐔((n+1)++)+⋯+𝐔(N)        #M213 ∵ P12,P190 Bounded Context Synonym.
    𝐮(n) = n+1+𝐔((n+1)++)+⋯+𝐔(N)   #E214 ∵ P207.
    𝐮(n+1) = n+1+𝐔((n+1)++)+⋯+𝐔(N) #P215 ∵ A196.
    𝐮(n) = 𝐮(n+1)                  #E216 ∵ P207.
    #

    # Prove: 𝐮(0) = N.
    𝐮(0) = 𝐮(1); 𝐮(n) = 𝐮(n+1) #C217 ∵ E206,E216.
    𝐮(0) = 𝐮(M)                #M218 ∵ A86,C217 Induction.
    𝐮(M) = M+𝐔((M)++)+⋯+𝐔(N)   #P219 ∵ A196.
    = M+𝐔(M++)+⋯+𝐔(N)          #P220 ∵ M18 Context Ungrouping.
    = M+𝐔(N)+⋯+𝐔(N)            #M221 ∵ P12,A75 Bounded Context Synonym.
    = M+𝐔(N)                   #P222 ∵ A34 Terminal Series Ellipsis.
    = M+1                      #M223 ∵ P11,P191 Right Bounded Synonym.
    = N                      <⊢#E116 ∵ A75 N Succeeds M.
    𝐮(0) = N                   #E224 ∵ P197.
    #

    # Prove: Σ[1,N]{n|𝐔(n)} = N.
    Σ[1,N]{n|𝐔(n)} = 1+𝐔(1++)+⋯+𝐔(N) <⊢#E195 ∵ P192.
    = 1+𝐔((1)++)+⋯+𝐔(N)              <⊢#P203 ∵ A17 Context Grouping.
    = 𝐮(1)                             #M225 ∵ A4,P205 Symmetric.
    = 𝐮(0)                             #M226 ∵ A4,E206 Symmetric.
    = N                              <⊢#E224 ∵ P197.
    Σ[1,N]{n|𝐔(n)} = N                 #E227 ∵ P192.
    #

    # Prove: Σ[1,N]{n|1} = N.
    𝐔(n) = 1           #P228 ∵ D185.
    N = Σ[1,N]{n|𝐔(n)} #M229 ∵ A4,E227 Symmetric.
    = Σ[1,N]{n|1}      #M230 ∵ P12,P228 Bounded Context Synonym.
    Σ[1,N]{n|1} = N    #E231 ∵ P192.
    #

###<a name="U7Q"></a> Σₙ,𝓊ₙ

    𝓊(n) = 𝓊ₙ  ⊢#A232 Index n.
    𝓊(m) = 𝓊ₘ  ⊢#A233 Index m.

    Σ{n|𝓈} = Σₙ{𝓈}  ⊢#A234 Summation Over n.
    Σ{m|𝓈} = Σₘ{𝓈}  ⊢#A235 Summation Over m.

    Σ{𝓈} = Σₙ{𝓈} :⊢#D236 Implied Summation Over n.

    Σ{n|𝓊(n)} = Σₙ{𝓊(n)} #P237 ∵ A234 Summation Over n.
    = Σₙ{𝓊ₙ}             #M238 ∵ P12,A232 Bounded Context Synonym.
    Σ{n|𝓊(n)} = Σₙ{𝓊ₙ}   #E239 ∵ P237.

    Σ{m|𝓊(m)} = Σₘ{𝓊(m)} #P240 ∵ A235 Summation Over m.
    = Σₘ{𝓊ₘ}             #M241 ∵ P12,A233 Bounded Context Synonym.
    Σ{m|𝓊(m)} = Σₘ{𝓊ₘ}   #E242 ∵ P240.

    Σₙ{𝓊ₙ} = 𝓊ₙ+⋯    :⊢#D243 Infinite Series Indexed By n.
    = 𝓊ₙ+𝓊ₙ₊₁+⋯        #P244 ∵ A35 Series Successor Ellipsis.
    Σₙ{𝓊ₙ} = 𝓊ₙ+𝓊ₙ₊₁+⋯ #E245 ∵ P237.

    # Prove: Σ{n|𝐟(n)} = 𝐟(0)+𝐟(1)+⋯.
    𝔽{𝐟}                   ⊢#A246 Some Function p.
    Σ{n|𝐟(n)} = 𝐟(0)+⋯      #P247 ∵ A173 Infinite Series.
    = 𝐟(0)+𝐟(0++)+⋯         #P248 ∵ A33 Series Successor Ellipsis.
    = 𝐟(0)+𝐟(1)+⋯           #M249 ∵ P12,M53 Bounded Context Synonym.
    Σ{n|𝐟(n)} = 𝐟(0)+𝐟(1)+⋯ #P250 ∵ E181.

    # Prove: Σ[1,3]{n|𝐟(n)} = 𝐟(1)+𝐟(2)+𝐟(3).
    Σ[1,3]{n|𝐟(n)} = 𝐟(1)+⋯+𝐟(3)    #P251 ∵ A172 Series.
    = 𝐟(1)+𝐟(1++)+⋯+𝐟(3)            #P252 ∵ A33 Series Successor Ellipsis.
    = 𝐟(1)+𝐟(2)+⋯+𝐟(3)              #M253 ∵ P12,M54 Bounded Context Synonym.
    = 𝐟(1)+𝐟(2)+𝐟(2++)+⋯+𝐟(3)       #P254 ∵ A33 Series Successor Ellipsis.
    = 𝐟(1)+𝐟(2)+𝐟(3)+⋯+𝐟(3)         #M255 ∵ P12,M55 Bounded Context Synonym.
    = 𝐟(1)+𝐟(2)+𝐟(3)                #P256 ∵ A34 Terminal Series Ellipsis.
    Σ[1,3]{n|𝐟(n)} = 𝐟(1)+𝐟(2)+𝐟(3) #E257 ∵ P251.
    #

###<a name="zcN"></a> ×

    𝓊×𝓋 = Σ[𝓊]{|𝓋} ⊢#A258 Multiplication.
    𝓊×1 = 𝓊       ⊢⊢#T259 Multiplicative Identity.

    3×4 = Σ[3]{|4}          #P260 ∵ A258 Multiplication.
    = 4|1+⋯+4|3             #P261 ∵ E178.
    = 4|1+4|(1++)+⋯+4|3     #P262 ∵ A37 Series Successor Ellipsis.
    = 4|1+4|(2)+⋯+4|3       #M263 ∵ P12,M54 Bounded Context Synonym.
    = 4|1+4|2+⋯+4|3         #P264 ∵ M18 Context Ungrouping.
    = 4|1+4|2+4|(2++)+⋯+4|3 #P265 ∵ A37 Series Successor Ellipsis.
    = 4|1+4|2+4|(3)+⋯+4|3   #M266 ∵ P12,M55 Bounded Context Synonym.
    = 4|1+4|2+4|3+⋯+4|3     #P267 ∵ M18 Context Ungrouping.
    = 4|1+4|2+4|3           #P268 ∵ A38 Terminal Series Ellipsis.
    Σ[3]{|4} = 4|1+4|2+4|3  #E269 ∵ P260.

    4|2+4|3 = 4+4 #P270 ∵ A170 Labeled Sum.
    4|1+4 = 4+4   #P271 ∵ A171 Labeled Sum.

    4|1+4|2+4|3 = 4|1+4+4 #M272 ∵ P11,P270 Right Bounded Synonym.
    = 4+4+4               #M273 ∵ P10,P271 Left Bounded Synonym.

    3×4 = 4+4+4   #E274 ∵ P260.

Just as with `+`, `-`,
whenever I use `×`,
it'll have the properties has in `ℕ`:

    𝓊×𝓋 = 𝓋×𝓊 ⊢⊢#T275 Commutative.

###<a name="fAs"></a> -
Subtraction:

    𝓊+𝓋 = 𝓍+𝓎 ⇒ 𝓊-𝓎 = 𝓍-𝓋 ⊢#A276 Subtraction.
    𝓊-𝓎 = 𝓍-𝓋 ⇒ 𝓊+𝓋 = 𝓍+𝓎 ⊢#A277 Subtraction.
    0-𝓋 = -𝓋              ⊢#A278 Negative Number.
    -𝓋 = 0-𝓋               #M279 Negative Number ∵ A4,A278 Symmetric.

    # Prove: 𝓋-𝓎 = -𝓎+𝓋
    0+𝓋 = 𝓋+0   #P280 ∵ T168 Commutative.
    0-𝓎 = -𝓎    #P281 ∵ A278 Negative Number.
    𝓋-𝓎 = 0+𝓋-𝓎 #M282 ∵ P10,M156 Left Bounded Synonym.
    = 𝓋+0-𝓎     #M283 ∵ P10,P280 Left Bounded Synonym.
    = 𝓋+(0-𝓎)   #P284 ∵ A15 Right Grouping.
    = (0-𝓎)+𝓋   #P285 ∵ T168 Commutative.
    = 0-𝓎+𝓋     #P286 ∵ M14 Left Ungrouping.
    = -𝓎+𝓋      #M287 ∵ P10,P281 Left Bounded Synonym.
    𝓋-𝓎 = -𝓎+𝓋  #E288 ∵ M282.
    #

###<a name="XIb"></a> /
Division:

    𝓊×𝓋 = 𝓍×𝓎 ⇒ 𝓊/𝓎 = 𝓍/𝓋  ⊢#A289 Division.
    𝓊/𝓎 = 𝓍/𝓋 ⇒ 𝓊×𝓋 = 𝓍×𝓎  ⊢#A290 Division.
    𝓊/1 = 𝓊               :⊢#D291 Whole Number.

    # Prove: 4/2 = 2
    2×2 = Σ[2]{|2}      #P292 ∵ A258 Multiplication.
    = 2|1+⋯+2|2         #P293 ∵ E178.
    = 2|1+2|(1++)+⋯+2|2 #P294 ∵ A37 Series Successor Ellipsis.
    = 2|1+2|(2)+⋯+2|2   #M295 ∵ P12,M54 Bounded Context Synonym.
    = 2|1+2|2+⋯+2|2     #P296 ∵ M18 Context Ungrouping.
    = 2|1+2|2           #P297 ∵ A38 Terminal Series Ellipsis.
    = 2+2               #P298 ∵ A170 Labeled Sum.
    = 2+1++             #M299 ∵ P11,A45 Right Bounded Synonym.
    = 2+1+1             #M300 ∵ P11,P163 Right Bounded Synonym.
    = 3+1               #M301 ∵ P10,E128 Left Bounded Synonym.
    = 4               <⊢#D129.
    2×2 = 4             #E302 ∵ P292.
    4×1 = 4             #P303 ∵ T259 Multiplicative Identity.
    4×1 = 2×2           #E304 ∵ P292.
    4/2 = 2/1           #M305 ∵ A289,E304 Division.
    = 2                 #P306 ∵ D291 Whole Number.
    4/2 = 2             #E307 ∵ M305.
    #
    GOT UP TO HERE

###<a name="r5l"></a> ℤ

    ℤ = ℕ{𝔩,𝔫|𝔩-𝔫} ⊢#A248 Integers.
    ℤ{𝔩-𝔫}          #M249 Number Subtractions Are Integers ∵ A94,A248 Iterators are sets.

    ℤ{i,j,k}        ⊢#A250 Integer Variables.

    ℤ{n-m} #P251 ∵ M249 Number Subtractions Are Integers.

###<a name="22g"></a> ℨ 𝔦,𝔧,𝔨

    ℨ /[ijk]/   !⊢
    ℨ { 𝔦,𝔧,𝔨 } !⊢
    ℤ{𝔦-𝔧}       ⊢#A252 Integer Subtraction Is Closed.

    ℤ{j-k} #P253 Integer Subtraction Is Closed ∵ A252 Integer Subtraction Is Closed.

###<a name="mgl"></a> ℚ


    ℚ = ℤ{i,j|i/j} ⊢#A97 Rationals.
    ℚ{r,s}         ⊢#A98 Rational Variables.
    ½ = 1/2  ⊢#A99 One Half.
    ℚ{½}

###<a name="ubG"></a> ⁿ,ᵐ

    𝕊{ⁿ,ᵐ,¹,²,³,⁴,⁵,⁶,⁷,⁸,⁹,⁰}  ⊢# Superscript.
    ⁿ∈𝕊

###<a name="SB5"></a> ₙ,ₘ

    𝕤{ₙ,ₘ,₁,₂,₃,₄,₅,₆,₇,₈,₉,₀}  ⊢# Subscripts.
    ₘ∈𝕤

    +𝓊+⋯ ⇒ +𝓊+𝓊+⋯ ⊢
    ∀+𝓊𝔞+⋯ ⇒ +𝓊𝔞+𝓊𝔞₊₁+⋯ ⊢
    ,𝓊𝔞,⋯ ⇒ ,𝓊𝔞,𝓊𝔞₊₁,⋯ ⊢
    +𝓊𝔟+⋯+𝓊𝔞 ⇒ +(₍𝔟₊₁<𝔞₎? 𝓊𝔟+𝓊𝔟₊₁+⋯+𝓊𝔞 : (𝔟₊₁=𝔞)? 𝓊𝔟+𝓊𝔞 : 𝓊𝔞)  ⊢# TODO: Not sure if this works.

###<a name="MIM"></a> Precedence rules
The following precedence rules are in order:

    𝓊𝓋𝓌 ⇒ (𝓊𝓋)𝓌     ⊢# Default way to read expressions.
    𝓅 𝓊 𝓆 ⇒ 𝓅 𝓊(𝓆)  ⊢#
    𝓅 𝓋𝓌 ⇒ 𝓅 (𝓋𝓌)   ⊢# "Σ 𝓊𝓋" means "Σ{𝓊𝓋}", not "Σ{𝓊}𝓋".
    𝓅 𝓆 ⇒ (𝓅)𝓆      ⊢#
    𝓃𝓊 ⇒ (𝓃𝓊)       ⊢# 2 and ½ bind right.  I don't think I use any other literal values.
    𝓋𝓌ᵘ ⇒ 𝓋(𝓌ᵘ)     ⊢# Left binding superscript.
    𝓋𝓌ᵤ ⇒ 𝓋(𝓌ᵤ)     ⊢# Left binding subsdript.
    𝓌ᵘᵥ ⇒ (𝓌ᵥ)ᵘ     ⊢# This weirdness is due to the sin²(x)=sin(x)*sin(x) convention.
    𝓊! ⇒ (𝓊!)       ⊢# Factorial is a left binding operator.

    # Examples:
    #
    𝓊2𝓋𝓌 = 𝓊2𝓋𝓌
    𝓊(2𝓋)𝓌 = 𝓊2𝓋𝓌
    (𝓊(2𝓋))𝓌 = 𝓊2𝓋𝓌
    #
    𝓊½𝓋𝓌 = 𝓊½𝓋𝓌
    𝓊(½𝓋)𝓌 = 𝓊½𝓋𝓌
    (𝓊(½𝓋))𝓌 = 𝓊½𝓋𝓌
    #
    𝓊 ½ 𝓋𝓌 = 𝓊 ½ 𝓋𝓌
    𝓊 ½ (𝓋𝓌) = 𝓊 ½ 𝓋𝓌
    𝓊 ½(𝓋𝓌) = 𝓊 ½ 𝓋𝓌
    𝓊 (½(𝓋𝓌)) = 𝓊 ½ 𝓋𝓌
    #
    𝓊½ 𝓋 𝓌 = 𝓊½ 𝓋 𝓌
    𝓊½ 𝓋(𝓌) = 𝓊½ 𝓋 𝓌
    𝓊½ (𝓋(𝓌)) = 𝓊½ 𝓋 𝓌
    (𝓊½)(𝓋(𝓌)) = 𝓊½ 𝓋 𝓌
    #
    𝓊!𝓋𝓌 = 𝓊!𝓋𝓌
    (𝓊!)𝓋𝓌 = 𝓊!𝓋𝓌
    ((𝓊!)𝓋)𝓌 = 𝓊!𝓋𝓌
    #
    2³₄ = 2³₄
    (2₄)³ = 2³₄   # This is not 8₄.  I would just write (2₄)³ to avoid confusion.
    2³₄ = (2₄)³

Some of these rules help compact the notation as it most commonly appears.
For example, √2πx is √[2π]x, but √nπx is √[n]πx.

###<a name="frL"></a> uᵥ
Subscripts (or indeces) labels a specific form of a more general expression:

    𝓊ᵥ[𝓌₀,⋯] = 𝓊[ᵥ,𝓌₀,⋯]     ⊢# Note that 𝓊ᵥ may ignore 𝓌,⋯ so as to be 𝓊[𝓋].
    𝓊ₙₘ[𝓌₀,⋯] = 𝓊[ₙ,ₘ,𝓌₀,⋯]  ⊢

Sequences can be thought of the set {𝓊ₙ}, but in this "paper",
𝓊ₙ is always a well defined expression.

###<a name="4bK"></a> 𝓊{𝓋ₙ}
A set of labeled (indexed) items:

    ℕ{n|𝓊ₙ} = {𝓊₀,𝓊₁,⋯}       ⊢
    ℕ[m,n] = {m,⋯,n}          ⊢
    ℕ[m,n]{i|𝓊ᵢ} = {𝓊ₘ,⋯,𝓊ₙ}  ⊢

###<a name="zJL"></a> Σ[l,k]{j|uⱼ}
[Series](http://en.wikipedia.org/wiki/Series_%28mathematics%29):

    Σ[l,k]{j|uⱼ} ≡ uₗ+⋯+uₖ

    # Examples:
    Σ[1,5]{m|m} = 1 + 2 + 3 + 4 + 5
    Σ[1,3]{m|m+m} = (1+1) + (2+2)+ (3+3)

###<a name="vkP"></a> n×u
Just regular [multiplication](http://en.wikipedia.org/wiki/Multiplication):

    n×u ≡ Σ[1,n]{u}
    nu ≡ n×u
    n/m × u/v ≡ (n×u)/(m×v)

###<a name="uyg"></a> ×⋯

    uₘ×⋯×uₙ ≡ (m<n)? uₘ×uₘ₊₁×⋯×uₙ : (m>n)? 1 : uₙ

###<a name="kJ6"></a> Σuₙ
Summation over Natural, ℕ, indeces:

    # Non-halting series.
    Σuₙ ≡ u₀+u₁+⋯ 
    ΣΣuₙₘ ≡ Σuₙ₀+Σuₙ₁+⋯ 

Note that by default a series will start with index 0.

###<a name="MlN"></a> Σₙuₙ
Halting series:

    Σₙuₙ ≡ Σ[0,M]{n|u[n]}
    ΣₙΣₘuₙₘ ≡ Σ[0,M]{n| Σ[0,M]{m| u[n,m]}}

    N = Σₙ 1 = Σ[0,M]{1} = Σ[1,M+1]{1} = Σ[1,N]{1}

TODO: [Telescoping Series](http://en.wikipedia.org/wiki/Telescoping_series)

###<a name="9XA"></a> ∞
Infinity:

    ∞ ≡ Σ1   # Does this work?

    ∞-1 = ∞
    # Proof
      ∞-1
      Σ1 - 1 
      (1+1+⋯) - 1       # Definition of Σuₙ
      (1 + 1+1+⋯) - 1   # Definition of 1+1+⋯
      (1+1+⋯) + 1 - 1
      (1+1+⋯) + 0
      (1+1+⋯)
      Σ1
      ∞

    ∞+1 = ∞
    # Proof:
      ∞-1 = ∞
      ∞-1+1 = ∞+1
      ∞+1-1 = ∞+1
      ∞+0 = ∞+1
      ∞ = ∞+1
      ∞+1 = ∞

Basically, one can add or subtract a finite number to ∞, it's still ∞.

    Σuₙ = Σ[0,∞]{n|uₙ}
    # Proof:
      Σuₙ = Σ[0,M]{n|uₙ}   # Assume...
      N = Σ1
      M = N-1 = Σ1 - 1 = ∞-1 = ∞
      Σuₙ = Σ[0,∞]{n|uₙ}   # I see!

One can absorb any integral multiple into ∞:

    N∞=∞
    # Proof:
      ∞
      Σ1
      1+1+⋯
      1 + 1+1+⋯
      (N-1) + 1+1+⋯
      (N-1)+(N-1)+⋯ + 1+1+⋯
      Σ(N-1) + Σ1
      ΣN
      NΣ1
      N∞  # It's equivalent to a proof by grouping.

One can absorb any 1/N multiple into ∞:

    ∞/N=∞
    # Proof:
      ∞/N
      Σ1/N
      1/N+1/N+⋯
      1/N + 1/N+1/N+⋯
      (N-1)/N + 1/N+1/N+⋯   # N-1 times and you almost get your first 1.
      (N-1)/N + 1/N+1/N+⋯
      ((N-1)/N+⋯) + (1/N+⋯)
      Σ[(N-1)/N] + Σ[1/N]
      Σ1
      ∞

One can absorb any rational multiple into ∞:

    (n/N)∞=∞
    # Proof:
      (n/N)∞
      (n)(1/N)∞
      (n)∞
      ∞

Regardless of the issues with ∞,
the propety I need of ∞ in definitions is that it's greater than any N:

    N < ∞
    # Proof:
      ∞
      Σ1
      ΣN          # I've shown this is also ∞
      N+N+⋯
      N+N+⋯ > N
      N < N+N+⋯
      N < ∞

Then, ∞ becomes a device to create non halting processes.
Some systems have 1/0=∞, but 0×∞=0×Σ1=Σ0×1=Σ0=0, and therefore also Σ0×Σ1=0.

    u/u=1 ↔ v/v=1 ↔ v=v×1 ↔ v/1=v
    u/u=1 ↔ 1/1=1 ↔ 1=1×1 ↔ 1/1=1 # gsub('v', '1')
    u/u=1 ↔ 0/0=1 ↔ 0=0×1 ↔ 0/1=0 # gsub('v', '0')
    u/u=1 ↔ ∞/∞=1 ↔ ∞=∞×1 ↔ ∞/1=∞ # gsub('v', '∞')

    1×u=u ↔ 1×v=v ↔ 1=v/v
    1×u=u ↔ 1×1=1 ↔ 1=1/1 # gsub('v', '1')
    1×u=u ↔ 1×0=0 ↔ 1=0/0 # gsub('v', '0')
    1×u=u ↔ 1×∞=∞ ↔ 1=∞/∞ # gsub('v', '∞')

    0×u=0 ↔ 0×v=0 ↔ 0=0/v ↔ v=0/0
    0×u=0 ↔ 0×∞=0 ↔ 0=0/∞ ↔ ∞=0/0 # gsub('v', '∞')
    0×u=0 ↔ 0×0=0 ↔ 0=0/0 ↔ 0=0/0 # gsub('v', '0')
    0×u=0 ↔ 0×1=0 ↔ 0=0/1 ↔ 1=0/0 # gsub('v', '1')

    u×(1/u)=1 ↔ v(1/v)=1
    u×(1/u)=1 ↔ 1(1/1)=1 # gsub('v', '1')
    u×(1/u)=1 ↔ 0(1/0)=1 # gsub('v', '0')
    u×(1/u)=1 ↔ ∞(1/∞)=1 # gsub('v', '∞')

    u>0,1/u>0 ↔ v>0,1/v>0
    u>0,1/u>0 ↔ ∞>0,1/∞>0 # gsub('v', '∞')
    u>0,1/u>0 ↔ 0>0,1/0>0 # gsub('v', '0')
    u>0,1/u>0 ↔ 1>0,1/1>0 # gsub('v', '1')

    # If we believe all of the above, then
    0/0 = {∞, 1, 0, v}

    # When does any of this make sense?
    0×u=r ↔ 0×v=r ↔ v=r/0 ↔ 0 = r/v
    0×u=r ↔ 0×1=r ↔ 1=r/0 ↔ 0 = r/1 # gsub('v', '1')
    0×u=r ↔ 0×0=r ↔ 0=r/0 ↔ 0 = r/0 # gsub('v', '0')
    0×u=r ↔ 0×∞=r ↔ ∞=r/0 ↔ 0 = r/∞ # gsub('v', '∞')

    # When does any of this make sense?
    u/0=r ↔ v/0=r ↔ v=0×r ↔ v/r=0
    u/0=r ↔ ∞/0=r ↔ ∞=0×r ↔ ∞/r=0 # gsub('v', '∞')
    u/0=r ↔ 0/0=r ↔ 0=0×r ↔ 0/r=0 # gsub('v', '0')
    u/0=r ↔ 1/0=r ↔ 1=0×r ↔ 1/r=0 # gsub('v', '1')

###<a name="zQw"></a> ∑
Sum over Integer, ℤ, indeces:

    ∑uₗ ≡ Σ[-∞,∞]{l|uₗ}     # ⋯+u₋₁+u₀+u₁+⋯
    ∑uₗ = Σuₙ + Σu-ₙ - u₀   # Take out the extra u₀

Notice that the symbol ∑ is sligtly taller than the symbol Σ.
Basically I'm creating shorthand notations for sums over ℤ vs. sums over ℕ.

###<a name="Jt7"></a> ⋅
The dot operator:

    {uₗ}⋅{vₗ} ≡ ∑ uₗvₗ

###<a name="IK3"></a> {⋯}⋅{⋯}
OK, so I'm a bit suspicious of ∞.
Consider this:

    {1,1,⋯}⋅{0,1,⋯}
    0+1+1+⋯
    1+1+⋯
    1+1+⋯
    Σ1
    ∞

Yes, the sum is unbounded, but the one of the objects that created it has a hole.
And it really is a different object than the one without a hole.
The regular infinity produced by `1+1+...` is both a sink and a source, but
did I really loose the hole?

###<a name="tky"></a> ∑ₗ
Halting sum over Integer, ℤ, indeces:

    ∑ₗuₗ ≡ Σ[-M,M]{l|uₗ}   # Halting version of ∑

    ∑ₗ1 = 2M+1 = 2N-1

###<a name="J5V"></a> Π
Products of sequences,
[Π](http://en.wikipedia.org/wiki/Multiplication#Capital_Pi_notation):

    # 1.upto(m).inject(1){|v,n|v×u[n]}
    Π[1,m]{n|uₙ} ≡ u₁×⋯×uₘ
    Π[1,0]{n|uₙ} = 1   # See definition of ⋯, for m<n uₘ×⋯×uₙ=1.

    # Examples:
    Π[1,2]{u} = u×u
    Π[1,3]{n|n} = 1×2×3

###<a name="y3Z"></a> uᵛ
Superscripts normally are ℕ denoting repetition:

    uⁿ ≡ Π[1,n]{u}
    u⁰=1
    u¹=u
    u²=uu    # Square
    u³=uuu   # Cube

    uᵐₙ ≡ (uₙ)ᵐ         # I don't use uₙ², but it's probably u[n²].
    uⁿ[v] ≡ (u[v])ⁿ
    u²[v] = u[v]×u[v]   # For example: "sin²(x) = sin(x)sin(x)"

Superscripts also denotes power or raising operations:

    uᵛ ≡ u^v   # or "u**v" in Ruby.

###<a name="8wf"></a> √u
[Squareroot](http://en.wikipedia.org/wiki/Square_root):

    √[u²]≡u
    √u²=u   # By precedence rules and definition.
    √[uu]=u

###<a name="fxq"></a> |u|
[Absolute value](http://en.wikipedia.org/wiki/Absolute_value):

    |u|≡(u>0)?u:-u  ←  ℚ{u}

###<a name="3r3"></a> ↓,↑
Arrow Operators on subscripts:

    uₗ↑ ≡ uₗ₊₁
    uₗ↓ ≡ uₗ₋₁

    uₗ↑² ≡ uₗ↑↑
    uₗ↑² = uₗ₊₂

    uₗ↓² ≡ uₗ↓↓
    uₗ↓² = uₗ₋₂

    uₗ↑ⁿ ≡ uₗ₊ₙ
    uₗ↓ⁿ ≡ uₗ₋ₙ

    Σₙu↑ ≡ Σₙuₙ₊₁   # Where context allows, subscript not needed.

###<a name="1U2"></a> ↧,↥

    u↥ ≡ u₀↑   # Step up from "ground", just to make notation "pretty" later on.
    u↥ = u₁

    u↧ ≡ u₀↓   # Step down from "ground".
    u↧ = u₋₁

    u↥ⁿ ≡ uₙ
    u↧ⁿ ≡ u₋ₙ

###<a name="U10"></a> Σu↑

    Σₙuₙ = +u₀ + Σₙuₙ₊₁ - u[N]
    Σₙuₙ = +u₀ + Σₙu↑ - u[N]

    Σuₙ = u₀ + Σu↑

###<a name="Uf9"></a> ∑u↑

    ∑ₗuₗ = +u[-M] + ∑ₗuₗ₊₁ - u[N]
    ∑ₗuₗ = +u[-M] + ∑ₗu↑ - u[N]

    ∑uₗ = ∑u↑   # It's the same!
    # Proof:
      ∑u↑
      Σ[-∞,∞]{u↑}
      Σ[-∞,∞]{uₗ+₁}
      Σ[-∞+1,∞+1]{uₗ}
      Σ[-∞,∞]{uₗ}

###<a name="blg"></a> ∑u↓

    ∑ₗuₗ = -u[-N] + ∑ₗuₗ₋₁ + u[M]
    ∑ₗuₗ = -u[-N] + ∑ₗu↓ + u[M]

    ∑uₗ = ∑u↓   # Same!

###<a name="vGe"></a> 𝐿
The limit fuction, 𝐿.
N is very, very, big!
Let's try a simple limit function:

    𝐿 Σuₙ ≡ 𝐿 Σₙuₙ               # 𝐿 truncates the series to down to N elements.
    𝐿[u+v] ≡ 𝐿[u] + 𝐿[v]
    𝐿[u] ≡ (|u| ≥ 1/N²)? u : 0   # 𝐿 ignores very small numbers.

    𝐿 Σₙ{1/N} = Σₙ 𝐿[1/N]
      = Σₙ{1/N}
      = 1   # Notice that this would have been 0 had I set the threshold to ≥ 1/N.

    𝐿 Σₙ{1/N²} = Σₙ 𝐿[1/N²]
      = Σₙ 0
      = 0   # Is this acceptable?

    Σₙ{1/N²} = 0.5 ← N=2        # n=2; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ{1/N²} = 0.25 ← N=4       # n=4; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ{1/N²} = 0.125 ← N=8      # n=8; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ{1/N²} = 0.0625 ← N=16    # n=16; n.times.inject(0){|s,i|s+1.0/(n*n)}
    Σₙ{1/N²} = 0.03125 ← N=32   # n=32; n.times.inject(0){|s,i|s+1.0/(n*n)}

As N doubles, the sum Σₙ{1/N²} halves.
So Σₙ{1/N²} does approach zero as N goes on to infinity.
For the following examples, I use factorial N! and the exponential function:

    𝐿[u+1/N²] = u
    𝐿[u+:Exponential[N]/N!] = u   # Try N≥10.
    𝐿[u+(v^N)/N!] = u             # N depends on v, but for some N it's true.
    𝐿[u+:Exponential[-N]] = u     # Obviously, I hope.

    |u| ≤ 1/N, |v| ≤ 1/N  →  |uv| ≤ 1/N², 𝐿[uv]=0

The Float::EPSILON for Ruby on my machine is about 2.22e-16.
So 𝐿 puts a limit on N on my machine of about 6.71e+7 (2.22e-16 ~ 1/(6.71e+7)^2).

###<a name="CuZ"></a> uₒ≡Σuₙ
I'll use subcript o, ₒ, to refer to the object that represents an infinite sum.

    uₒ≡Σuₙ

###<a name="yfS"></a> ℝ
For the purpose of this "paper", Real, ℝ, just needs to include the series I'm working with.
That is ℝ augments ℚ with Σuₙ as follows:

    ℚ{uₙ: |uₙ|≤1/n² ← n≥N}, v=Σuₙ ↔ ℝ{v}, ℚ{𝐿[Σₙuₙ]}

So I just need ℝ to work with 𝐿[Σuₙ].
ℝ has well defined + and ×:

    uₒ=Σuₙ,vₒ=Σvₙ → uₒ+vₒ ≡ Σ uₙ+vₙ, uₒvₒ ≡ ΣΣ uₙvₘ

ℝ can be scaled by a rational:

    ℚ{v,uₙ}, ℝ{uₒ:uₒ=Σuₙ} → vuₒ = vΣuₙ = Σvuₙ, ℝ{vuₒ}

Quick plausibility check:

    u=[1,2,3],v=[4,5,6] →
      uₒ = Σuₙ = 1 + 2 + 3 = 6
      vₒ = Σvₙ = 4 + 5 + 6 = 15
      # Addition
      uₒ+vₒ = Σ uₙ+vₙ = (1+4) + (2+5) + (3+6) = 5 + 7 + 9 = 21
      Σuₙ + Σvₙ = 6 + 15 = 21
      uₒ+vₒ = Σuₙ+Σvₙ = Σ uₙ+vₙ = 21   # All self consistent
      # Multiplication
      uₒvₒ = ΣΣ uₙvₘ = ((1×4)+(1×5)+(1×6)) + ((2×4)+(2×5)+(2×6)) + ((3×4)+(3×5)+(3×6))
        = (4+5+6) + (8+10+12) + (12+15+18)
        = 15 + 30 + 45
        = 90
      uₒvₒ = Σuₙ Σvₙ = 6×15 = 90
      uₒvₒ = Σuₙ Σvₙ = ΣΣ uₙvₘ = 90   # Again, consistent.
      # Division we don't have in the same form.
      uₒ/vₒ = Σuₙ/Σvₙ

    Σuₙ Σvₘ = ΣΣ uₙvₘ
    # The rigorous proof:
      Σuₙ Σvₘ
      (Σuₙ)×(Σvₘ)   # Just explicitly showing what I mean.
      Σ{uₙ×(Σvₘ)}   # Treat the v series like a number and take it into the u series.
      Σ{Σ{uₙvₘ}}    # uₙ is just a constant rational and can go into the v series.
      ΣΣ{uₙvₘ}      # Well... maybe it was obvious to begin with.

    # Same for ∑∑
    ∑∑ uₗvₖ = ∑uₗ × ∑vₗ

I'll be using ΣΣ{uₙvₘ}=Σ{uₙ}Σ{vₙ} later.
In general I'll refer to a and b as Real number:

    ℝ{A,B,a,b}   # a and b are Real numbers.

###<a name="pZX"></a> x,t
[Position](http://en.wikipedia.org/wiki/Position_(vector)) and
[time](http://en.wikipedia.org/wiki/Time):

    ℝ{x,t}

In general, x would be a vector (ℝ,ℝ,ℝ), but
I'll only be working with one dimension.

Note that time is measure by observing a physical clock.
I believe this will create a [paradox](http://en.wikipedia.org/wiki/Paradox)
because I assume there's no error in its measurement.
To resolve the paradox someone (no not me, I'm done!)
will have to do the dual Energy-Time problem.

###<a name="iyp"></a> ∞/∞
One can absorb any Real multiple into ∞:

    uₒ∞=∞
    # Proof:
       uₒ∞
       ∞uₒ
       ∞Σuₙ
       Σ∞uₙ
       Σ∞
       ∞Σ1
       ΣΣ1
       (1+1+⋯)+(1+1+⋯)+⋯
       ∞  # or ∞² ?

If √4={-2,2}, then can I say:

    ∞/∞ = ℝ
    # Proof:
      ∞/∞
      uₒ∞/∞  # Poops out any real number!
      uₒ     # LOL!

###<a name="rNP"></a> 𝜖≡a/∞
[Infinitesimal](http://en.wikipedia.org/wiki/Infinitesimal).

    𝜖≡a/∞   # Any r/∞ gives 𝜖.
    𝜖×∞=ℝ

    𝜖₁≡1/∞₁
    𝜖₁×∞₁=1

    # In either version,
    a,0<𝜖<|a|<∞

> TODO: Note that I did not construct ∞₁. How? :-??
> I'm guessing ∞₁ is one of an orthogonal set in ∞.
> It would really be a great convenience.  Conjecture:

    𝜖₁×∞ = 𝜖×∞₁ = 1
    # Proof:
      # TODO: Needs a construction of ∞₁.

> Maybe I'll just stick to the notion of big N.

###<a name="5qT"></a> Σrⁿ
Just a quick review of
[Geometric series](http://en.wikipedia.org/wiki/Geometric_series):

    ℚ{r:0<r<1}

    Σₙrⁿ = (1-r^N)/(1-r)
    # Proof:
      u = Σₙrⁿ
      u = Σ[0,M]{n|rⁿ}
      u = r⁰+r¹+⋯+r^M
      u = r⁰+r¹+⋯+r^(N-1)   # M=N-1
      ru = r(r⁰+r¹+⋯+r^(N-1)) = r¹+r²+⋯+r^N
      u-ru = r⁰+r¹+⋯+r^(N-1) - r¹+r²+⋯+r^N
      u-ru = r⁰-r^N
      u(1-r) = r⁰-r^N
      u = (r⁰-r^N)/(1-r)

    𝐿 Σrⁿ = 1/(1-r)
    # Proof:
      𝐿 Σrⁿ
      # Notice that ⋯ expands out indefinitely giving a non-halting sum.
      𝐿 r⁰+r¹+r²+⋯+r^∞
      # Hey! It's simple algebra. Formula for the geometric series.
      𝐿 (1-r^∞)/(1-r)
      (1-𝐿[r^∞])/(1-r)
      (1-0)/(1-r)
      1/(1-r)

The reason I bring this up now is that as r approaches 1,
the series approaches ∞ quite literally!

    r=1-𝜖₁ →
      𝐿 Σ(1-𝜖₁)ⁿ
      1/(1-(1-𝜖₁))
      1/(1-1+𝜖₁)
      1/(0+𝜖₁)
      1/𝜖₁
      ∞₁
      Σ1

###<a name="s2N"></a> ⅀

    ⅀uₙₘ ≡ ΣΣuₙₘ

###<a name="SuG"></a> ⨋ₓ

    ⨋ₓuₗₖ ≡ ∫ₓ⅀uₗₖ[x] = ∫ₓ∑∑uₗₖ[x]

Note that for the harmonic oscillator, uₗₖ will take the form uₙvₘ.
Nonetheless, it will still be a sum over the integers where uₙvₘ=0 if n or m < 0.

###<a name="Ama"></a> ℂ
Complex numbers:

    ℂ ≡ (ℝ,ℝ)
    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)+(vᵣ,vᵢ)≡(uᵣ+vᵣ,uᵢ+vᵢ)
      (uᵣ,uᵢ)(vᵣ,vᵢ)≡(uᵣvᵣ-uᵢvᵢ,uᵣvᵢ+uᵢvᵣ)
      (uᵣ,uᵢ)(uᵣ,uᵢ)=(uᵣ²-uᵢ²,2uᵣuᵢ)
      uᵣ≡(uᵣ,0)

In general I'll refer to α and β as Complex numbers:

    ℂ{α,β}   # α and β are Complex numbers.

###<a name="NLb"></a> ℯ
[Exponential](http://en.wikipedia.org/wiki/Exponential_function#Formal_definition)
series definition:

    :Exponential[u] ≡ Σ uⁿ / n!
    ℯ[u] ≡ :Exponential[u]
    ℯᵘ ≡ ℯ^(u) ≡ ℯ[u]   # Alternate forms.

###<a name="ZE8"></a> Sine
[Sine](http://en.wikipedia.org/wiki/Sine#Series_definition)
series definition:

    :Sine[u] ≡ Σ (-1)ⁿ u^(2n+1) / (2n+1)!
    S[u] ≡ :Sine[u]

    Sᵤ = Σ 𝔩ⁿu^n↥₂/n↥₂!   # Isn't this fun!
    # Proof:
      :Sine[u] = Σ (-1)ⁿ u^(2n+1) / (2n+1)!
      S[u] = Σ (-1)ⁿ u^(2n+1) / (2n+1)!
      Sᵤ = Σ (-1)ⁿ u^(2n+1) / (2n+1)!   # Sᵤ=S[u,...]
      Sᵤ = Σ 𝔩ⁿ u^(2n+1) / (2n+1)!      # 𝔩=-1
      Sᵤ = Σ 𝔩ⁿu^n↥₂/n↥₂!               # n↥₂=2n↥=2(n+1)

###<a name="CgT"></a> Cosine
[Cosine](http://en.wikipedia.org/wiki/Trigonometric_functions#Series_definitions)
series definition:

    :Cosine[u] ≡ Σ (-1)ⁿ u^(2n) / (2n)!
    C[u] ≡ :Cosine[u]

    Cᵤ = Σ 𝔩ⁿu^(2n)/(2n)!

So n↥₂ may not be the appropriate thing to use describe S after all.

###<a name="FU8"></a> 𝑖
The Imaginary number 𝑖:

    𝑖 ≡ (0,1)
    𝑖² = (-1,0)
    # Proof
      (0,1)(0,1)
      (0²-1²,0×1+1×0)
      (-1,0)
    (u,v) = u+𝑖v
    𝑖² = -1

###<a name="XXd"></a> &#42;
Complex conjugation:

    (u,v)* ≡ (u,-v)
    (u+𝑖v)* = u-𝑖v
    ℯ[𝑖]* = (C+𝑖S)* = C-𝑖S = ℯ[-𝑖]   # what it does to e

    ℝ{uᵣ,uᵢ,vᵣ,vᵢ} →
      (uᵣ,uᵢ)*(vᵣ,vᵢ)=(uᵣvᵣ+uᵢvᵢ,uᵣvᵢ-uᵢvᵣ)
      (uᵣ,uᵢ)*(uᵣ,uᵢ)=(u²ᵣ+v²ᵢ,0)
      (uᵣ,0)*(vᵣ,0)=(uᵣvᵢ,0)
      uᵣ*vᵣ=uᵣvᵣ   # Notice how it does end up looking like multiplication in ℝ.

      # Just to review
      (uᵣ,uᵢ)×(vᵣ,vᵢ) = (uᵣvᵣ-uᵢvᵢ, uᵣvᵢ+uᵢvᵣ)
      (uᵣ,uᵢ)×(uᵣ,uᵢ) = (u²ᵣ-u²ᵢ, 2uᵣuᵢ)
      (uᵣ,uᵢ)*(vᵣ,vᵢ) = (uᵣvᵣ+uᵢvᵢ, uᵣvᵢ-uᵢvᵣ)
      (uᵣ,uᵢ)*(uᵣ,uᵢ) = (u²ᵣ+u²ᵢ, 0)

Maybe `*` should really be thought as a binary operator,
a special type of multiplication.

###<a name="FD0"></a> 𝒟ₓ
The [derivative](http://en.wikipedia.org/wiki/Derivative):

    :Derivative{x|Σ αₙxⁿ} ≡ Σ nαₙxⁿ⁻¹

    𝒟ₓu[x] ≡ :Derivative{x|u[x]}

###<a name="9Ql"></a> 𝒟(u⋅v)=𝒟u⋅v+u⋅𝒟v
Dot Product Rule for 𝒟:

    𝒟 {uₙ}⋅{vₙ} = 𝒟 Σ uₙvₙ =  Σ 𝒟 [uₙvₙ] = Σ 𝒟[uₙ]vₙ + uₙ𝒟[vₙ]
    𝒟 {uₙ}⋅{vₙ} = Σ{𝒟[uₙ]vₙ} + Σ{uₙ𝒟[vₙ]}
    𝒟 {uₙ}⋅{vₙ} = {𝒟 uₙ}⋅{vₙ} + {uₙ}⋅{𝒟 vₙ}

###<a name="iPk"></a> ∫
The [integral](http://en.wikipedia.org/wiki/Integral):

    :Integral[a,b]{x|𝒟ₓu[x]} = u[b]-u[a]

    ∫ₓu[x] ≡ :Integral[-∞,∞]{x|u[x]}

    2 = ∫ₓ𝜖₁
    # Proof:
      ∫ₓ𝜖₁
      :Integral[-∞,∞]{x|𝜖₁}
      :Integral[-∞,∞]{x|𝒟ₓ[𝜖₁x]}
      ∞₁×𝜖₁ - -∞₁×𝜖₁
      ∞₁×𝜖₁ + ∞₁×𝜖₁
      1 + 1
      2

    2∞₁ = ∫ₓ1
    # Proof:
      ∫ₓ1
      :Integral[-∞,∞]{x|1}
      :Integral[-∞,∞]{x|𝒟ₓ[x]}
      (∞₁) - (-∞₁)
      ∞₁ + ∞₁
      2∞₁

Why not?
LOL

###<a name="zaX"></a> n!
Factorial:

    n! ≡ Π[1,n]{u|u}   # 1×2×3×...×n

    u[n]=1/n! → u[n-1]=nu[n]   # Recursion
    # Proof:
      nu[n]                    # Given
      n/n!                     # Substitution
      n/((n-1)!n)
      1/(n-1)!
      u[n-1]

    1/(-1)! = 0
    # Proof 1:
      n=0, 1/(n-1)!=n/n!
      1/(0-1)! = 0/0!   # Substitute n.
      1/(-1)! = 0/1     # 0! is just 1
      1/(-1)! = 0
    # Proof 2, by recursion:
      u[-1]
      u[0-1]
      0u[0]
      0/0!
      0/1
      0

    1/(-2)! = 0
    # Proof by recursion:
      u[-2]
      u[-1-1]
      -1u[-1]
      -1×0
      0   # In general 1/u! = 0 ← ℤ{u<0}

###<a name="qsc"></a> (ⁿₘ)
[Binomial coefficient](http://en.wikipedia.org/wiki/Binomial_coefficient),
n choose m:

    (ⁿₘ) ≡ n!/(m!(n-m)!)

###<a name="t99"></a> nₘ
I'd like to make the following refinement in ℕ,
[Factoral](http://www.urbandictionary.com/define.php?term=Factoral&defid=5895569) forward:

    n₀ ≡  1
    nₘ ≡ (n+m)nₘ₋₁

    n₁ = (n+1)n₀ = n+1
    n₂ = (n+2)n₁ = (n+2)(n+1)
    n₃ = (n+3)n₂ = (n+3)(n+2)(n+1)
    n₄ = (n+4)n₃ = (n+4)(n+3)(n+2)(n+1)

    m>0 → nₘ=Π[1,m]{l|n+l}

This is very close to [Pochhammer's](http://en.wikipedia.org/wiki/Pochhammer_symbol)
(or Knuth) notation for rising and falling factorials.
Pochhammer has n(¹)=n, n(²)=n(n+1), while n(₁)=n, n(₂)=n(n-1).
But these do not match the algebra of the problem I'm working on as
I'll need n↥(rising by one) to be n+1 and n↧(lowering by one) to be 1/n.
Nonetheless, note that n(ₘ)=1/n₋ₘ

###<a name="KLm"></a> 0ₘ

    0ₘ = Π[1,m]{l|0+l} = Π[1,m]{l|l} = m!
    0₀ = 1   # by definition
    0₁ = (0+1)1 = 1  = 1!
    0₂ = (0+2)1 = 2  = 2!
    0₃ = (0+3)2 = 6  = 3!
    0₄ = (0+4)6 = 24 = 4!
    ⋯
    0ₘ = m!

###<a name="ngq"></a> 1ₘ

    1₀ = 1   # by definition
    1₁ = (1+1)1  = 2   = 2!
    1₂ = (1+2)2  = 6   = 3!
    1₃ = (1+3)6  = 24  = 4!
    1₄ = (1+4)24 = 120 = 5!
    1ₘ = (m+1)!
    ⋯
    1ₘ = (m+1)!

###<a name="eUd"></a> 2ₘ

    2₀ = 1   # by definition
    2₁ = (2+1)1  = 3   = 6/2   = 3!/2
    2₂ = (2+2)3  = 12  = 24/2  = 4!/2
    2₃ = (2+3)12 = 60  = 120/2 = 5!/2
    2₄ = (2+4)60 = 360 = 720/2 = 6!/2
    ⋯
    2ₘ = (2+m)!/2

###<a name="pOG"></a> 3ₘ

    3₀ = 1   # by definition
    3₁ = (3+1)1   = 4    = 24/6   = 4!/3!
    3₂ = (3+2)4   = 20   = 120/6  = 5!/3!
    3₃ = (3+3)20  = 120  = 720/6  = 6!/3!
    3₄ = (3+4)120 = 840  = 5040/6 = 7!/3!
    ⋯
    3ₘ = (3+m)!/3!

###<a name="vOj"></a> nₘ=(n+m)!/n!

    nₘ=(n+m)!/n!
    # Proof:
      nₘ
      Π[1,m]{l|n+l}                 # (n+1)*(n+2)*...*(n+m)
      Π[1+n,m+n]{l|l}               # Same thing!
      Π[1,m+n]{l|l} / Π[1,n]{l|l}   # (1*2*...*n) * (n+1)*(n+2)*...*(n+m) / (1*2*...*n)
      (m+n)! / n!

###<a name="w4y"></a> n₋ₘ=(n-m)!/n!

    nₘ₊₁ = (n+m+1)nₘ   # by defintion ↑
    nₘ₊₁/(n+m+1) = nₘ
    nₘ = nₘ₊₁/(n+m+1)

    n₋₁ = n₀/(n-1+1)
    n₋₁ = 1/n

    n₋₂ = n₋₁/(n-2+1)
    n₋₂ = 1/(n(n-1))

    n₋₃ = 1/(n(n-1)(n-2))
    n₋₄ = 1/(n(n-1)(n-2)(n-3))

    n₋ₘ = (n-m)!/n!  ← m≤n   # Amazing, works backwards too!

###<a name="6OO"></a> n₋ₙ=1/n!

    n₋ₙ = 1/(n(n-1)⋯(n-n+1)) = 1/(n(n-1)⋯(1)) = 1/n!
    n₋ₙ₋₁ = 1/(n!(0))
    n₋ₙ₋₂ = 1/(n!(0)(-1))
    n₋ₙ₋₃ = 1/(n!(0)(-1)(-2))
    n₋ₘ = (-1)ᵐ⁻ⁿ⁺¹/(n!0(m-n+1)!) ← m>n   # Anyways, a division by zero.

###<a name="SoK"></a> (ⁿₘ)=m-ₘ/n-ₘ

    (ⁿₘ) = m-ₘ/n-ₘ   # or m↧ᵐ/n↧ᵐ
    # Proof
      (ⁿₘ)
      n!/(m!(n-m)!)
      n!/(m!n!n-ₘ)
      1/(m!n-ₘ)
      m-ₘ/n-ₘ

    # Some random exercises on nₘ
    0ₙn₋ₙ = (n!)(1/n!) = 1
    n₁1ₙ = (n+1) (1+1)⋯(1+n) = (n+1)² (1+1)⋯(n) = (n₁)²1ₙ₋₁
    2₃1₃ = (2+1)(2+2)(2+3) (1+1)(1+2)(1+3) =  3*4*5 * 2*3*4 = 2*(3*4)²*5 = 1₁(2₂)²4₁
    5₂8₈ = 6*7 * 9*⋯*16
    1₆5₆ = 2*⋯*7 * 6*⋯*11 = 2*⋯*5 * (6*7)² * 8*⋯*11 = 1₄(5₂)²7₄
    15₄5₁₆ = 16*⋯*19 * 6*⋯21 = 6*⋯*15 * (16*⋯*19)² * 20*21 = 5₁₀(15₄)²19₂

###<a name="I4Q"></a> n↥,n₀,n↧
Arrows meaningful as Factorals:

    n↥↑² = n↥³ = (n+1)(n+2)(n+3)
    n₀↑² = n↥² = (n+1)(n+2)
    n₀↑ = n↥  = n+1
    n₀        = 1
    n₀↓ = n↧  = 1/n
    n₀↓² = n↧² = 1/(n(n-1))
    n↧↓² = n↧³ = 1/(n(n-1)(n-2))

###<a name="jL9"></a> nᵥn!
Factoral with Factorial:

    nᵥn! = (n+v)!

    n₃n! = (n+1)(n+2)(n+3)n! = (n+3)!   # OK

    n-₃n! = n!/(n(n+1)(n+2))
    n-₃n! = (n-3)!(n-2)(n-1)n/(n(n-1)(n-2))
    n-₃n! = (n-3)!   # OK

    n↥n! = (n+1)!
    n↧n! = (n-1)!

    n↥²n! = (n+2)!
    n↧²n! = (n-2)!

    n↥ᵐn! = (n+m)!
    n↧ᵐn! = (n-m)!

###<a name="44r"></a> ŉ
Division by n in the notation can be cumbersome.
It's all about condensing the notation:

    ŉ ≡ 1/n
    ŉ! = 1/n!

###<a name="Yv1"></a> ʼu
Sometimes I need ŉ to be a different letter:

    ʼu ≡ 1/u
    ʼuv = vʼu = v/u

###<a name="4H1"></a> u↑ˡᵥ
Operations with Arrows often result in an extra factor.
I'm adding notation for that:

    u↑ˡᵥ ≡ u↑ˡvˡ
    u↥ˡᵥ = u↥ˡvˡ
    √u↥ˡᵥ = √[u↥ˡvˡ]
    √u↥ᵥ = √[u↥v]
    2n = 1/n↧₂ = ŉ↧₂
    √2n = √ŉ↧₂

Why do √2n=√ŉ↧₂ ?
Well, if its the final result √2n is the answer.
But √ŉ↧₂ really means the function(of l) √ŉ↧ˡ₂, where l=1.

    √ŉ↧⁰₂ = 1
    √ŉ↧¹₂ = √2n
    √ŉ↧²₂ = √[2²n(n-1)] = √[4n(n-1)]
    √ŉ↧³₂ = √[8n(n-1)(n-2)]
    # ...
    √ŉ↧ˡ₂ = √[2ˡn!/(n-l)!]
    # Proof:
      √ŉ↧ˡ₂
      √[1/n↧ˡ₂]             # ŉ=1/n
      √[1/(2⁻ˡn↧ˡ)]         # ↧ˡ₂ means ↧ˡ2⁻ˡ
      √[2ˡ/(n↧ˡ)]           # 1/2⁻ˡ=2ˡ
      √[2ˡ/n₋ₗ]             # n↧ˡ=n₋ₗ in subscript notation
      √[2ˡ/((n₋ₗ)!/(n!))]   # nₘ=(n+m)!/n!
      √[2ˡn!/(n₋ₗ)!]

The √ŉ↧ˡ₂ shortens notation to 5 characters, from 14 in √[2ˡn!/(n-l)!].
And I'll end up not having to calculate any of it in the problem later, because
it will all cancel out!
And while they're there, they nicely show the structure of the algebra.

    n↥⁰₂ = 1
    n↥¹₂ = 2(n+1)
    n↥²₂ = 4(n+1)(n+2)
    n↥³₂ = 8(n+1)(n+2)(n+3)
    # ...
    n↥ˡ₂ = 2ˡ(n+l)!/n!   # 4 characters vs. 11.

Subscripts are not always available, so here's an alternate notation:

    (u,v)↑ˡ ≡ u↑ˡᵥ
    (u,v)↑ˡ = vˡu↑ˡ
    (u,ʼv)↑ˡ = u↑ˡ/vˡ

    (u,ʼv)↥^l = u↥ˡ/vˡ
    (u,ʼv):Up^l = u↥ˡ/vˡ
    (u,1/v):Up^l = u↥ˡ/vˡ   # When all you have is ASCII

    # Still shorter than the standard ASCII expansion.
    n↥ˡ₂ = (n,2):Up^l = 2^l(n+l)!/l!

> TODO: I should give a pure ASCII description to everything else too.

###<a name="wNn"></a> 𝔩

    𝔩 ≡ -1
    𝔩² = 1
    𝔩ⁿ = (-1)ⁿ   # Just to compact notation.

    𝔩ⁿ = (n%2=0)? 1 : -1   # Used to add when even, subtract when odd.

###<a name="IwS"></a> S²+C²=1
[Trigonometric Identities](http://en.wikipedia.org/wiki/List_of_trigonometric_identities):

    S²+C²=1            # Pythagoras
    S[u+v]=SᵤCᵥ+CᵤSᵥ   # Sine's angle sum
    C[u+v]=CᵤCᵥ-SᵤSᵥ   # Cosine's angle sum
    C[2u]=1-2S²ᵤ       # Cosine double angle "cos(2u)=1-2sin²(u)"

Just a quick exercise.
Derivation: Cosine's Angle Sum to Cosine Double Angle:

    :Cosine[2u]
    C[2u] = C[2u]
    C[2u] = C[u+u]
    C[2u] = C[u]C[u]-S[u]S[u]
    C[2u] = CᵤCᵤ-SᵤSᵤ         # Shorten form
    C[2u] = CC-SS             # From context, C=:Cosine[u] and S=:Sine[u]
    C[2u] = C²-S²
    C[2u]-1 = C²-S²-1
    C[2u]-1 = (C²-1)-S²
    C[2u]-1 = (-S²=C²-1)-S²   # A bit of "rubyism" here.  Just invoking Pythagoras.
    C[2u]-1 = -S²-S²
    C[2u]-1 = -2S²
    C[2u] = 1-2S²
    # I should expand out the context once the shorthand has fulfilled its purpose.
    C[2u] = 1-2S²[u]
    :Cosine[2u] = 1 - 2:Sine²[u]

###<a name="VkX"></a> ℯⁱᵘ=Cᵤ+𝑖Sᵤ
Known properties of e:

    ℯ[u]ℯ[v] = ℯ[u+v]
    ℯ[𝑖u] = C[u]+𝑖S[u]
    ℯ[-𝑖u] = C[u]-𝑖S[u]
    ℯ[0] = 1

###<a name="VuP"></a> 𝛿
[Dirac delta function](http://en.wikipedia.org/wiki/Dirac_delta_function):

    𝛿ₗₖ ≡ (l=k)? 1 : 0 # :all

###<a name="nXb"></a> ⧼v⧽
For some N>0, which is less than infinity,
consider function u and v such that:

    ∫ₓ (αu[x])*(βv[x]) ≤ N < ∞

Then the Dirac notation is defined as follows:

    ⧼αu|βv⧽ ≡ ∫ₓ (αu[x])*(βv[x])

For the case I'm working in,
u and v are a discrete set of orthogonal functions:

    ∫ₓ uₗ*uₖ = (l=k)? ∫ₓuₗ² : 0

Specifically, they can be normalized to be a set of ortho-normal functions:

    ∫ₓ uₗ*uₖ = 𝛿ₗₖ   # (l=k)? 1 : 0

    ⧼αu|βv⧽ = ∫ₓ ∑∑ (αuₗ)*(βvₖ)

    ⧼αu|βv⧽ = α*⧼u|βv⧽ = β⧼αu|v⧽
    ⧼αu|βv⧽* = ⧼βv|αu⧽
    ⧼αu| + ⧼βv| = ⧼αu+βv|   # Liboff's 4.24.

I will try to use BRA-KETS literally by the given definition: `⧼u|v⧽≡∫{∑uₗ*∑vₗ}`.
The way BRA-KETS are sometimes used, the u and v in ⧼u|v⧽ are just labels of the state,
in which case Liboff's equation 4.24 can make no sense!

    ⧼αu|βu⧽ = (α*β)∑ uₗ*uₗ   # Orthogonal, crossterms are all 0.

    ⧼v⧽ ≡ ⧼u|vu⧽ = ⧼v†u|u⧽   # Where u is known from context.

    |ₖ⧽ ≡ |uₖ⧽   # Labeled KET, where u is know from context.

    ⧼u|ₖ⧽ = ⧼ₖ|ₖ⧽
    # Proof
      ⧼u|ₖ⧽
      ⧼u|uₖ⧽
      ∫{∑uₗ*uₖ}
      ∫{uₖ*uₖ}   # u are orthogonal, only the k-th term contributes.
      ⧼uₖ|uₖ⧽
      ⧼ₖ|ₖ⧽

    # TODO: What I mean by average value,  ⧼u⧽ ≡ Σₙuₙ/N ?

###<a name="2ef"></a> Δ²
Measure of uncertainty defined (4.1a):

    Δ²[u] ≡ ⧼(u - ⧼u⧽)²⧽
    Δ²u ≡ ⧼(u - ⧼u⧽)²⧽   # Allow the shorter form if unambiguous.

    Δ[u] ≡ √[Δ²u]   # I only defined Δ² and a not in terms of Δ, so...
    Δu ≡ √[Δ²u]     # Again, allow the shorter form.

    # Deriving 4.1b:
    Δ²u = ⧼u² - 2u⧼u⧽ + ⧼u⧽²⧽
    Δ²u = ⧼u²⧽ - 2⧼u⧽⧼u⧽ + ⧼u⧽²
    Δ²u = ⧼u²⧽ - 2⧼u⧽² + ⧼u⧽²
    Δ²u = ⧼u²⧽ - ⧼u⧽²

Measure of uncertainty (4.1b):

    Δ²u = ⧼u²⧽ - ⧼u⧽²

###<a name="Uz0"></a> 𝑃
𝑃 is the [Poisson distribution](http://en.wikipedia.org/wiki/Poisson_distribution):

    𝑃ₙ ≡ uⁿℯ[-u]/n!
    Σ 𝑃ₙ = 1
    0 ≤ 𝑃ₙ ≤ 1
    ⧼u⧽ = Σ 𝑃ₙuₙ

###<a name="2on"></a> 𝑝

    𝑝ₙ ≡ √[uⁿℯ[-u]/n!]
    𝑝ₙ*𝑝ₙ = 𝑃ₙ
    # Proof
      𝑝ₙ*𝑝ₙ
      √[uⁿℯ[-u]/n!]*√[uⁿℯ[-u]/n!]
      √[uⁿℯ[-u]/n!]√[uⁿℯ[-u]/n!]   # It's just all real.
      uⁿℯ[-u]/n!
      𝑃ₙ

###<a name="IRG"></a> 𝒫
Shorthand for `𝑝ₙ*𝑝ₘ`, 𝒫ₙₘ:

    𝒫ₙₘ ≡ 𝑝ₙ*𝑝ₘ

Arrows on 𝒫 will act on m:

    𝒫ₙ₍ₘ₊₁₎ = 𝒫ₙₘ↑ = 𝒫↑
    𝒫ₙ₍ₘ-₁₎ = 𝒫ₙₘ↓ = 𝒫↓
    𝒫ₙ₍ₙ₊₁₎ = 𝒫↑𝛿
    𝒫ₙ₍ₙ-₁₎ = 𝒫↓𝛿

###<a name="ZMc"></a> 𝒫↑↓≠𝒫↓↑

     𝒫↑↓≠𝒫↓↑
     # Proof:
       𝒫↑↓≠𝒫↓↑
       𝑝ₙ↑*𝑝ₘ↓≠𝑝ₙ↓*𝑝ₘ↑
       𝑝[n+1]*𝑝[m-1]≠𝑝[n-1]*𝑝[m+1]

Basically 𝑝ₙ↑, 𝑝ₘ↓, 𝑝ₙ↓, and 𝑝ₘ↑ are four different values.
Just like in general I have to say `a*b≠c*d`.
But even if n=m when 𝑝 is Complex:

    𝑝[n+1]*𝑝[n-1]≠𝑝[n-1]*𝑝[n+1]   # α*β≠β*α
    # Proof:
      α*β≠β*α
      (A+𝑖a)*(B+𝑖b)≠(B+𝑖b)*(A+𝑖a)
      (A-𝑖a)(B+𝑖b)≠(B-𝑖b)(A+𝑖a)
      AB +A𝑖b -𝑖aB -𝑖a𝑖b ≠ BA +B𝑖a -𝑖bA -𝑖b𝑖a
      AB +A𝑖b -𝑖aB -𝑖𝑖ab ≠ BA +B𝑖a -𝑖bA -𝑖𝑖ba
      AB +A𝑖b -𝑖aB +ab ≠ BA +B𝑖a -𝑖bA +ba
      AB+ab +𝑖(Ab-aB) ≠ BA+ba +𝑖(Ba-bA)
      AB+ab +𝑖(Ab-aB) ≠ AB+ab +𝑖(aB-Ab)
      (Ab-aB) ≠ (aB-Ab)
      Ab ≠ aB

###<a name="DZ0"></a> 𝛿𝒫↑↓=𝛿𝒫↓↑&#42;

    𝛿𝒫↑↓=𝛿𝒫↓↑*
    𝑝ₙ₊₁*𝑝ₙ-₁ = (𝑝ₙ-₁*𝑝ₙ₊₁)*

So let 𝑝ₙ₊₁ be any α and let 𝑝ₙ-₁ be any β:

    α*β=(β*α)*
    # Proof:
      α*β
      (A+𝑖a)*(B+𝑖b)
      (A-𝑖a)(B+𝑖b)
      AB +A𝑖b -𝑖aB -𝑖a𝑖b
      AB +𝑖Ab -𝑖aB -𝑖𝑖ab
      AB +𝑖Ab -𝑖aB +ab
      AB+ab + 𝑖(Ab-aB)
      (AB+ab - 𝑖(Ab-aB))*
      (AB+ab + 𝑖(aB-Ab))*
      (BA+ba + 𝑖(Ba-bA))*
      (BA +ba +𝑖Ba -𝑖bA)*
      (BA +𝑖Ba -𝑖bA +ba)*
      (BA +𝑖Ba -𝑖bA -𝑖𝑖ba)*
      ((B-𝑖b)(A+𝑖a))*
      ((B+𝑖b)*(A+𝑖a))*

###<a name="y3s"></a> κ,μ
I think the point here is that these values are "measured" by "experiment" in "some way".

[Mass](http://en.wikipedia.org/wiki/Mass) and
[spring contant](http://en.wikipedia.org/wiki/Hooke%27s_law):

    ℝ{μ}   # Mass, μ b/c m is already used.
    ℝ{κ}   # Spring constant.

###<a name="vmD"></a> π
You can check that there exist several series 
of rational terms that produce [π](http://en.wikipedia.org/wiki/Pi).
[Leibniz formula for π](http://en.wikipedia.org/wiki/Leibniz_formula_for_π):

    ℝ{π} ← π = 4 Σ (-1)ⁿ/(2n+1)
    # Proof:
      π
      4 Σ (-1)ⁿ/(2n+1)
      4 Σ 1/(2(2n)+1) - 1/(2(2n+1)+1)   # pairing the alternating series
      4 Σ 1/(4n+1) - 1/(4n+3)
      4 Σ ((4n+3)-(4n+1))/((4n+1)(4n+3))
      4 Σ 2/((4n+1)(4n+3))
      Σ 8/((4n+1)(4n+3))
        # Fits given definition of ℝ.
        |8/((4n+1)(4n+3))| ≤ |8/(16n²)| ≤ |1/(2n²)| ≤ 1/n² ← n≥N

Since I do not computationally define division by ℝ,
1/√2π may be problematic, but there is series for that:

    1/√2π = 2/9801 Σ (4n)!(1103+26390k)/((k!)⁴(396⁴^k))
    1/√2π = 2/9801 Σ (4n)!(1103+26390k)/((k!)⁴(396⁴ᵏ))

Anyways, I think I can trust [algebra](http://en.wikipedia.org/wiki/Algebra)
to say π/π=1, and if the final result of the algebra is Rational(ℚ),
I won't worry about it.  OK!

###<a name="SB2"></a> ½!
From the [Gamma and Pi functions](http://en.wikipedia.org/wiki/Factorial#The_Gamma_and_Pi_functions):

    ½! = ½√π

> Because I don't believe in coincidence of this type.
> I think I've seen ½√π somewhere in the problem.

###<a name="1Xb"></a> ℏ
[Reduced Planck constant](http://en.wikipedia.org/wiki/Planck_constant):

    ℝ{ℎ}
    ℏ ≡ ℎ/2π

###<a name="Jji"></a> ω

    ω² ≡ κ/μ   # Angular frequency
    ω = √[κ/μ]

###<a name="0h7"></a> f

    f ≡ ω/(2π)   # Frequency

###<a name="2Xh"></a> Eₙ

    Eₙ ≡ ωℏ(n+½)   # 3.2: Energy eigen-value

###<a name="0bH"></a> 𝐱

    𝐱 ≡ x

###<a name="w6M"></a> 𝐩

    𝐩 ≡ -𝑖ℏ𝒟ₓ

###<a name="mo3"></a> Δ²𝐩

TODO:

###<a name="8SV"></a> Δ²𝐱

TODO:

###<a name="bST"></a> [𝐱,𝐩]

TODO: want to explain how it relates to Δ𝐱Δ𝐩.

###<a name="bdY"></a> 𝐇

TODO:

###<a name="WEu"></a> ⌽ᵗₙ
Time evolution:

    # NOTE! The ½ part makes this object a bit of a screw ball.
    ⌽ᵗₙ ≡ ℯ[-𝑖ω(n+½)t] = ℯ[-𝑖Eₙt/ℏ]
    φᵗₙ ≡ ℯ[-𝑖ωnt]   # "How do I end up with this?" I may ask.

    ⌽ₙ*⌽ₘ = φₘ-ₙ   # You don't have to explicitly show time if it can be infered.
    # Proof:
      ⌽ₙ*⌽ₘ
      ⌽-ₙ⌽ₘ
      ℯ[𝑖ω(n+½)t - 𝑖ω(m+½)t]
      ℯ[-𝑖ω(m-n)t]
      φₘ-ₙ

    # Don't have to explicitly show quantum number if it can be infered.
    ⌽⁰ = 1
    ⌽¹ = ℯ[-𝑖ω(n+½)]
    # Just to show that the notation makes sense.
    ⌽ᵗ = (⌽¹)^t = ℯ[t × (-𝑖ω(n+½))] = ℯ[-𝑖ω(n+½)t]

> Why is equation [7.17](TIME.md) `-𝑖Eₙt/ℏ` and not `+𝑖Eₙt/ℏ`?
> It looks to me to be a convention and
> in Liboff's book it stems from defining `Û ≡ ℯ[-𝑖tĤ/ℏ]`.

###<a name="fzU"></a> 𝕌{⌽}
⌽ is [Unitary](http://en.wikipedia.org/wiki/Unitary_matrix):

    u*u=1 ↔ 𝕌{u}   # Definition of Unitary.

    𝕌{⌽}
    # Proof:
      ⌽ᵗₙ*⌽ᵗₙ
      ℯ[-𝑖ω(n+½)t]*ℯ[-𝑖ω(n+½)t]
      ℯ[+𝑖ω(n+½)t]×ℯ[-𝑖ω(n+½)t]
      ℯ[𝑖ω(n+½)t - 𝑖ω(n+½)t]
      ℯ[0]
      1   # Therefore ⌽ is Unitary.

###<a name="h8y"></a> ⌽→φ

    ⌽ₙ*⌽ₙ₊₁ = φₙ₊₁-ₙ = φ₁
    φ↥ ≡ φ₀↑ = φ₁   # This will make notation very consistent later.
    ⌽ₙ*⌽ₙ₊₁ = φ↥

    ⌽ₙ*⌽ₙ₋₁ = φₙ₋₁-ₙ = φ₋₁
    φ↧ ≡ φ₀↓ = φ₋₁
    ⌽ₙ*⌽ₙ₋₁ = φ↧

    ⌽ₙ*⌽ₙ₊₂ = φₙ₊₂-ₙ = φ₂ = φ↥²
    ⌽ₙ*⌽ₙ₋₂ = φₙ₋₂-ₙ = φ₋₂ = φ↧²

###<a name="zlN"></a> sₙ,cₙ
Short for Sine(nωt) and Cosine(nωt):

    sₙ ≡ S[nωt]
    cₙ ≡ C[nωt]
    c₂ₙ=1-2s²ₙ   # Cosine double angle in terms of c and s.

    φₙ = cₙ-𝑖sₙ   # φ in terms of c and s.

    φ₁ = c₁-𝑖s₁

    φ₋₁ = c₁+𝑖s₁   # Maybe that'll work.

    φ₁ + φ₋₁ = 2c₁
    φ↥ + φ↧ = 2c₁   # Remember this one!

    φ₁ - φ₋₁ = 2s₁
    φ↥ - φ↧ = 2s₁

    φ₂ = c₂-𝑖s₂
    φ₋₂ = c₂+𝑖s₂

    φ₋₂ + φ₂ = 2c₂
    φ↧² + φ↥² = 2c₂   # And remember this one!

###<a name="Ojo"></a> ñ
Average Quantum number ñ

    ⧼n⧽ = ⧼n|𝑝ₙ*n𝑝ₙ|m⧽ = Σ n𝑝ₙ𝑝ₙ = Σ n𝑃ₙ   # only n=m terms contribute

    ñ ≡ 𝐿 ⧼n⧽
    ñ = 𝐿 Σ n𝑃ₙ = 𝐿 Σₙ n𝑃ₙ   # Remember that 𝐿 truncates the series.

    Σₙ n𝑃ₙ = 𝐿 Σₙ nuⁿℯ[-u]/n!                    # Just by definition of 𝑃ₙ.
     = Σ[0,M]{n|nuⁿℯ[-u]/n!}                     # Definition of Σₙ.
     = 0 + Σ[1,M]{n|nuⁿℯ[-u]/n!}                 # The first element in the series is just zero.
     = Σ[1,M]{n|uⁿℯ[-u]/(n-1)!}                  # Have the n factor absorbed by the factorial.
     = Σ[0,M-1]{n|u[n+1]ℯ[-u]/n!}                # Shift.
     = uΣ[0,M-1]{n|uⁿℯ[-u]/n!}                   # Take out a factor of u.
     = u(Σ[0,M]{n|uⁿℯ[-u]/n!} - (u^M)ℯ[-M]/M!)   # Add and subtract the an Nth element (which is M).
     = u(Σₙ𝑃ₙ) - u(u^M)ℯ[-M]/M!                  # Definition of Σₙ and 𝑃ₙ.
     = u(1) - u^(M+1)ℯ[-M]/M!                    # Poisson distribution sums up to one.
     = u - u^(M+1)ℯ[-M]/M!

    ñ = 𝐿[u - u^(M+1)ℯ[-M]/M!]
    ñ = 𝐿[u] - 𝐿[u^(M+1)ℯ[-M]/M!]
    ñ = u - 0
    ñ = u   # As expected.  :)

Now I can describe the distribution in terms of the average quantum number:

    𝑃ₙ = ñⁿℯ[-ñ]/n!
    𝑝ₙ = √[ñⁿℯ[-ñ]/n!]

###<a name="k5Y"></a> Eₒ
Average energy eigen value, Eₒ:

    Eₒ = ωℏ(ñ+½)

TODO: There is more I could say here

###<a name="LJ7"></a> ñ²=𝐿Σ{n(n-1)𝑃ₙ}

    𝐿 Σ n(n-1)𝑃ₙ
    𝐿 Σₙ n(n-1)𝑃ₙ
    𝐿 Σₙ 1/n₋₂ uⁿℯ[-u]/n!
    𝐿 Σₙ uⁿℯ[-u]/(n-2)!
    𝐿 Σₙ u² u^(n-2)ℯ[-u]/(n-2)!
    𝐿 u² Σₙ u^(n-2)ℯ[-u]/(n-2)!
    𝐿 u² Σ[0,M]{n|u^(n-2)ℯ[-u]/(n-2)!}
    𝐿 u² Σ[-2,M-2]{n|uⁿℯ[-u]/n!}
    𝐿 u² (Σ[-2,-1]{n|uⁿℯ[-u]/n!} + Σ[0,M-2]{n|uⁿℯ[-u]/n!})
    𝐿 u² (Σ[-2,-1]{n|uⁿℯ[-u]/n!} + Σ[0,M-2]{n|𝑃ₙ})
    u²(𝐿[ℯ[-u]/(u²(-2)!)] + 𝐿[ℯ[-u]/(u(-1)!)] + 𝐿[Σ[0,M-2]{n|𝑃ₙ}])
    u²(0 + 0 + 𝐿[Σ[0,M-2]{n|𝑃ₙ}])   # 1/u! = 0 if integer u < 0
    u²(𝐿[Σ[0,M]{n|𝑃ₙ} - 𝑃[M-1] - 𝑃[M]])
    u²(𝐿[Σ𝑃ₙ - 𝑃[M-1] - 𝑃[M]] - 𝑃[M+1] - ⋯)   # Re-consider the infinite series.
    u²(𝐿[1 - 𝑃[M-1] - 𝑃[M]] - 𝑃[M+1] - ⋯)     # Σ𝑃ₙ = 1
    u²(1 - 𝐿[𝑃[M-1] - 𝑃[M]] - 𝑃[M+1] - ⋯)
    # To 𝐿, for large enough M, the trailing sequence are all zeroes.
    u²(1 - Σ0)
    u²(1-0)
    u²×1
    u²

    ñ² = 𝐿 Σ{n(n-1)𝑃ₙ}   # b/c ñ=u, so u²=ñ²

###<a name="mI6"></a> p→𝑃

    𝑝ₙ𝑝ₙ₊₁ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁺¹ℯ[-ñ]/(n+1)!]
           = √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!] √[ñ/(n+1)] 
           = 𝑝ₙ 𝑝ₙ √[ñ/(n+1)] 
           = 𝑃ₙ √[ñ/(n+1)] 
           = √[ñ/(n+1)]𝑃ₙ 
    𝑝ₙ𝑝ₙ₊₁ = √ñ𝑃ₙ/√n₁   # Using Factoral
    𝑝𝑝↑ = √ñ𝑃ₙ/√n↥      # And Arrow notation

    𝑝ₙ𝑝ₙ₋₁ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁻¹ℯ[-ñ]/(n-1)!]
           = √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!] √[n/ñ] 
           = 𝑝ₙ 𝑝ₙ √[n/ñ] 
           = 𝑃ₙ √[n/ñ] 
           = √[n/ñ]𝑃ₙ 
    𝑝ₙ𝑝ₙ₋₁ = 𝑃ₙ/√[ñn₋₁]   # Using Factoral
    𝑝𝑝↓ = 𝑃ₙ/√[ñn↧]       # And Arrow notation

    𝑝ₙ𝑝ₙ₊₂ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁺²ℯ[-ñ]/(n+2)!]
           = √[ñ²/((n+1)(n+2))] √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!]
           = ñ/√[(n+1)(n+2)] 𝑝ₙ𝑝ₙ
           = ñ/√[(n+1)(n+2)] 𝑃ₙ
    𝑝ₙ𝑝ₙ₊₂ = ñ𝑃ₙ/√n₂   # Using Factoral
    𝑝ₙ𝑝ₙ₊₂ = ñ𝑃ₙ/√n↥²  # Using Arrow

    𝑝ₙ𝑝ₙ₋₂ = √[ñⁿℯ[-ñ]/n!] √[ñⁿ⁻²ℯ[-ñ]/(n-2)!]
           = √[(n-1)n/ñ²] √[ñⁿℯ[-ñ]/n!] √[ñⁿℯ[-ñ]/n!]
           = √[(n-1)n]/ñ 𝑝ₙ𝑝ₙ
           = √[(n-1)n]/ñ 𝑃ₙ
    𝑝ₙ𝑝ₙ₋₂ = 𝑃ₙ/(ñ√n₋₂)   # Using Factoral
    𝑝ₙ𝑝ₙ₋₂ = 𝑃ₙ/(ñ√n↧²)   # Using Arrow

    𝑝 = √m↑𝑝↑/√ñ
    # Proof:
      𝑝𝑝↑ = √ñ𝑃/√m↥
      𝑝↑ = √ñ𝑝/√m↥
      √m↥𝑝↑/√ñ = 𝑝
      𝑝 = √m↥𝑝↑/√ñ

    𝑝 = √[ñm↓]𝑝↓  
    # Proof:
      𝑝𝑝↓ = 𝑃/√[ñm↧]
      𝑝↓ = 𝑝/√[ñm↧]
      √[ñm↧]𝑝↓ = 𝑝
      𝑝 = √[ñm↧]𝑝↓

    𝑝 = √m↥𝑝↑/√ñ = √[ñm↧]𝑝↓  
    𝑝 = √[m↥ˡ/ñˡ]𝑝↑ˡ

    𝑝 = √(m,ʼñ)↥ˡ 𝑝↑ˡ = √(m,ʼñ)↧ˡ 𝑝↓ˡ

###<a name="Pvg"></a> ξ
The non-dimensional displacement, ξ.

    ξ² ≡ μω/ℏ x²   # A.1b
    x² = ℏ/(μω) ξ²

###<a name="AXS"></a> ⨋

    ⨋uₗₖ ≡ ∫⅀uₗₖ[ξ] = ∫∑∑uₗₖ[ξ]

###<a name="8P4"></a> 𝒟

    𝒟 u[ξ] ≡ :Derivative{ξ|u[ξ]}

###<a name="FnP"></a> 𝛽

    𝛽² ≡ μω/ℏ

###<a name="hIf"></a> 𝒽

    𝒽 ≡ ℏ/(μω)

    𝒽 = 1/𝛽²
    𝛽 = 1/√𝒽

    ξ² = x²/𝒽 = ʼ𝒽x²
    # Proof:
      ξ² = μω/ℏ x²        # By definition.
      ξ² = ʼ(ℏ/(μω)) x²   # ʼu=1/u.
      ξ² = ʼ(𝒽) x²        # 𝒽≡ℏ/(μω)
      ξ² = ʼ𝒽 x²
      ξ² = x²/𝒽

    x² = 𝒽 ξ²
    x = √𝒽 ξ   = 𝛽ξ

###<a name="QcB"></a> 𝒟ₓξ

    𝒟ₓξ
    𝒟ₓ√[(μω/ℏ)x²]
    𝒟ₓ√[(μω/ℏ)]x
    √[(μω/ℏ)]𝒟ₓx
    √[(μω/ℏ)]
    √𝛽²
    𝛽
    1/√𝒽

###<a name="o8p"></a> 𝒟 x

    𝒟 x
    𝒟 √[ℏξ²/(μω)]
    𝒟 √[ℏ/(μω)] ξ
    √[ℏ/(μω)]𝒟 ξ
    √[ℏ/(μω)]
    √𝒽
    1/𝛽

###<a name="yYZ"></a> 𝐴ₙ
The Normalization Constant, 𝐴ₙ:

    𝐴ₙ ≡ 1/√[2ⁿn!√π]   # that really is 1/√√π in there.

    𝐴₀ = 1/√[2⁰0!√π]
    𝐴₀ = 1/√√π
    𝐴₀ = 1/√[2(½!)]   # ½! = ½√π
    𝐴₀ = √[½/½!]
    𝐴₀ = √[½/½!]      # I'm pretty sure this means something.

    𝐴ₙ/𝐴ₙ₋₁ = 1/√[2n]
    # Proof:
      (1/√[2ⁿn!√π]) / (1/√[2ⁿ⁻¹(n-1)!√π])
      (1/√[2ⁿn!√π]) × (√[2ⁿ⁻¹(n-1)!√π])
      √[2ⁿ⁻¹(n-1)!√π] / √[2ⁿn!√π]
      √[2ⁿ⁻¹(n-1)!] / √[2ⁿn!]   # √π cancels
      √[2ⁿ⁻¹] / √[2ⁿn]          # n!/(n-1)! = n
      1 / √[2n]                 # 2ⁿ/2ⁿ⁻¹ = 2

    # Identities:
    𝐴ₙ   = 𝐴ₙ₋₁ / √[2n]       # Given
    𝐴ₙ₊₁ = 𝐴ₙ   / √[2(n+1)]   # Increment index n
    𝐴ₙ   = 𝐴ₙ₊₁ × √[2(n+1)]   # Solve for 𝐴ₙ
    𝐴ₙ₋₁ = 𝐴ₙ   × √[2n]       # Decrement index n

    # With Factorals
    𝐴ₙ   = 𝐴ₙ₋₁ × √[½n₋₁] = 𝐴ₙ₋₁ × √[½n↧] = 𝐴ₙ₋₁ × √[½n↧]
    𝐴ₙ₊₁ = 𝐴ₙ   / √[2n₁]  = 𝐴ₙ   / √[2n↥] = 𝐴ₙ   / √[2n↥]
    𝐴ₙ   = 𝐴ₙ₊₁ × √[2n₁]  = 𝐴ₙ₊₁ × √[2n↥] = 𝐴ₙ₊₁ × √[2n↥]
    𝐴ₙ₋₁ = 𝐴ₙ   / √[½n₋₁] = 𝐴ₙ   / √[½n↧] = 𝐴ₙ   / √[½n↧]

    𝐴ₘ = √[2m↥]𝐴ₘ↑ = √[½m↧]𝐴ₘ↓
    # Note that arrows bind before literal values, so...
    𝐴ₘ = √2m↥𝐴ₘ↑ = √½m↧𝐴ₘ↓  # Use these.

    𝐴 = √2n↥𝐴↑ = √½n↧𝐴↓     # With context.
    𝐴 = √[2ˡn↥ˡ]𝐴↑ˡ = √n↥ˡ₂𝐴↑ˡ

    𝐴 = √(m,2)↥ 𝐴↑ = √(m,2)↧ 𝐴↓
    # or
    𝐴 = √m↥₂𝐴↑ = √m↧₂𝐴↓

###<a name="lQl"></a> 𝒢,ℊ
The [Gaussian](http://en.wikipedia.org/wiki/Gaussian_function) function:

    𝒢ₓ ≡ ℯ[-x²/2]
    𝒢  ≡ ℯ[-ξ²/2]

    𝒟ₓ𝒢ₓ = -x𝒢ₓ
    𝒟 𝒢  = -ξ𝒢

    ∫{x|𝒢ₓ} = √2π

    ℊₓ ≡ ℯ[-x²]
    ℊ  ≡ ℯ[-ξ²]

    𝒟ₓℊₓ = -2xℊₓ
    𝒟 ℊ  = -2ξℊ

    ∫{x|ℊₓ} = √π

    ℊ⁻¹ = ℯ[ξ²]
    ℊ⁻¹ℊ = ℯ[ξ²]ℯ[-ξ²] = ℯ[ξ²-ξ²] = ℯ[0] = 1

    𝒢𝒢=ℊ

###<a name="m3i"></a> ℋ
The [Hermite polynomials](http://en.wikipedia.org/wiki/Hermite_polynomials):

    ℋₙ[ξ] ≡ (-1)ⁿ ℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²]   # A.3, physicists' Hermite polynomials.
    ℋ = 𝔩ⁿʼℊ(𝒟)ⁿℊ   # Shorthand.

###<a name="mV6"></a> 𝒟ℋ

    𝒟 ℋₙ[ξ] = 2nℋₙ₋₁[ξ]   # A.4a
    𝒟 ℋ = 2nℋ↓   # Shorthand.
    # http://math.stackexchange.com/questions/581897/hermite-polynomials-recurrence-relation
    # Proof:
      𝒟 ℋₙ[ξ]                                               # Given
      𝒟[(-1)ⁿ ℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²]]                            # Substitution, definition of ℋ
      (-1)ⁿ 𝒟[ℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²]]                            # Take out the constant
      (-1)ⁿ (𝒟[ℯ[ξ²]] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²] 𝒟[(𝒟)ⁿ ℯ[-ξ²]])   # Product rule
      (-1)ⁿ (𝒟[ℯ[ξ²]] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²] (𝒟)ⁿ 𝒟[ℯ[-ξ²]])   # Well... obviously!
      (-1)ⁿ (2ξℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²] (𝒟)ⁿ -2ξℯ[-ξ²])    # Executing 𝒟
      # I don't remember ever coming across the General Leibniz rule
      # http://en.wikipedia.org/wiki/General_Leibniz_rule
      # Let (ⁿₘ) mean n choose m.
      (-1)ⁿ (2ξℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²] Σ[0,n]{m| (ⁿₘ) (𝒟)ᵐ[-2ξ] (𝒟)ⁿ-ᵐℯ[-ξ²]})
      # 𝒟²[-2ξ]=0, (𝒟)ⁿ[-2ξ]=0 if n>1.
      (-1)ⁿ (2ξℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²] Σ[0,1]{m| (ⁿₘ) (𝒟)ᵐ[-2ξ] (𝒟)ⁿ-ᵐℯ[-ξ²]})
      (-1)ⁿ (2ξℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²]((ⁿ₀) 𝒟⁰[-2ξ] (𝒟)ⁿ-⁰ℯ[-ξ²] + (ⁿ₁) 𝒟¹[-2ξ] (𝒟)ⁿ⁻¹ℯ[-ξ²]))
      (-1)ⁿ (2ξℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²](   1 𝒟⁰[-2ξ] (𝒟)ⁿ  ℯ[-ξ²] +    n 𝒟¹[-2ξ] (𝒟)ⁿ⁻¹ℯ[-ξ²]))
      (-1)ⁿ (2ξℯ[ξ²] (𝒟)ⁿ ℯ[-ξ²] + ℯ[ξ²](         -2ξ  (𝒟)ⁿ  ℯ[-ξ²] +     n   (-2)  (𝒟)ⁿ⁻¹ℯ[-ξ²]))
      (-1)ⁿ (2ξℯ[ξ²](𝒟)ⁿℯ[-ξ²] - 2ξℯ[ξ²](𝒟)ⁿℯ[-ξ²] - 2nℯ[ξ²](𝒟)ⁿ⁻¹ℯ[-ξ²])
      (-1)ⁿ (0 - 2nℯ[ξ²](𝒟)ⁿ⁻¹ℯ[-ξ²])
      (-1)ⁿ (-2) nℯ[ξ²](𝒟)ⁿ⁻¹ℯ[-ξ²]
      (-1)ⁿ⁻¹ 2 nℯ[ξ²](𝒟)ⁿ⁻¹ℯ[-ξ²]
      2n (-1)ⁿ⁻¹ ℯ[ξ²] (𝒟)ⁿ⁻¹ℯ[-ξ²]
      2n ℋₙ₋₁[ξ]
    # Shorthand Proof:
      𝒟 ℋ
      𝒟 𝔩ⁿʼℊ(𝒟)ⁿℊ
       𝔩ⁿ(𝒟[ʼℊ](𝒟)ⁿℊ + ʼℊ𝒟[(𝒟)ⁿℊ])
       𝔩ⁿ(𝒟[ʼℊ](𝒟)ⁿℊ + ʼℊ(𝒟)ⁿ𝒟[ℊ])
       𝔩ⁿ(2ξʼℊ(𝒟)ⁿℊ + ʼℊ(𝒟)ⁿ𝒟[ℊ])
       𝔩ⁿ(2ξʼℊ(𝒟)ⁿℊ + ʼℊ(𝒟)ⁿ[-2ξℊ])
       𝔩ⁿ(2ξʼℊ(𝒟)ⁿℊ + ʼℊΣ[0,n]{m|(ⁿₘ)(𝒟)ᵐ[-2ξ](𝒟)ⁿ⁻ᵐℊ})
       𝔩ⁿ(2ξʼℊ(𝒟)ⁿℊ + ʼℊΣ[0,1]{m|(ⁿₘ)(𝒟)ᵐ[-2ξ](𝒟)ⁿ⁻ᵐℊ})
       𝔩ⁿ(2ξʼℊ(𝒟)ⁿℊ + ʼℊΣ{(ⁿ₀)(𝒟)⁰[-2ξ](𝒟)ⁿ⁻⁰ℊ,(ⁿ₁)(𝒟)¹[-2ξ](𝒟)ⁿ⁻¹ℊ})
       𝔩ⁿ(2ξʼℊ(𝒟)ⁿℊ + ʼℊΣ{-2ξ(𝒟)ⁿℊ,n(-2)(𝒟)ⁿ⁻¹ℊ})
       𝔩ⁿ(2ξʼℊ(𝒟)ⁿℊ - 2ʼℊξ(𝒟)ⁿℊ - 2nʼℊ(𝒟)ⁿ⁻¹ℊ)
       𝔩ⁿ(- 2nʼℊ(𝒟)ⁿ⁻¹ℊ)
       𝔩ⁿ⁻¹(2nʼℊ(𝒟)ⁿ⁻¹ℊ)
       2n𝔩ⁿ⁻¹ʼℊ(𝒟)ⁿ⁻¹ℊ
       2nℋ↓

    𝒟 ℋₙ[ξ] = 2nℋₙ₋₁[ξ] = ℋₙ↓[ξ]/(½n↓)
    𝒟ℋ = 2nℋ↓ = ℋ↓/½n↧ = ℋ↓/n↧₂ = ŉ↧₂ℋ↓

###<a name="oNs"></a> ℋ↑

    ℋₙ₊₁[ξ] = 2ξℋₙ[ξ] - 2nℋₙ₋₁[ξ]   # A.4b
    ℋ↑ = 2ξℋ - 2nℋ↓   # Shorthand.
    # Proof:
      ℋₙ₊₁[ξ]
      (-1)ⁿ⁺¹ ℯ[ξ²] (𝒟)ⁿ⁺¹ ℯ[-ξ²]
      (-1)ⁿ(-1) ℯ[ξ²] (𝒟)ⁿ[𝒟 ℯ[-ξ²]]
      (-1)ⁿ(-1) ℯ[ξ²] (𝒟)ⁿ[(-2ξ) ℯ[-ξ²]]
      (-1)ⁿ     ℯ[ξ²] (𝒟)ⁿ[  2ξ  ℯ[-ξ²]]
      # General Leibniz rule
      (-1)ⁿ ℯ[ξ²] Σ[0,n]{m|(ⁿₘ) (𝒟)ᵐ[2ξ] (𝒟)ⁿ-ᵐ[ℯ[-ξ²]]}
      (-1)ⁿ ℯ[ξ²]((ⁿ₀) 𝒟⁰[2ξ] (𝒟)ⁿ-⁰[ℯ[-ξ²]] + (ⁿ₁) 𝒟¹[2ξ] (𝒟)ⁿ⁻¹[ℯ[-ξ²]] + 0 ⋯)   # Dejavu
      (-1)ⁿ ℯ[ξ²](   1   (2ξ) (𝒟)ⁿ  [ℯ[-ξ²]] +    n   (2)  (𝒟)ⁿ⁻¹[ℯ[-ξ²]])
      (-1)ⁿ ℯ[ξ²](2ξ(𝒟)ⁿ[ℯ[-ξ²]] + 2n(𝒟)ⁿ⁻¹[ℯ[-ξ²]])
      (-1)ⁿ ℯ[ξ²] 2ξ(𝒟)ⁿ[ℯ[-ξ²]] + (-1)ⁿ ℯ[ξ²] 2n(𝒟)ⁿ⁻¹[ℯ[-ξ²]]                    # Distribute
      2ξ (-1)ⁿ ℯ[ξ²] (𝒟)ⁿ[ℯ[-ξ²]] + 2n (-1)ⁿ ℯ[ξ²] (𝒟)ⁿ⁻¹[ℯ[-ξ²]]
      2ξ (-1)ⁿ ℯ[ξ²] (𝒟)ⁿ[ℯ[-ξ²]] + 2n (-1)(-1)ⁿ⁻¹ ℯ[ξ²] (𝒟)ⁿ⁻¹[ℯ[-ξ²]]
      2ξ (-1)ⁿ ℯ[ξ²] (𝒟)ⁿ[ℯ[-ξ²]] - 2n (-1)ⁿ⁻¹ ℯ[ξ²] (𝒟)ⁿ⁻¹[ℯ[-ξ²]]
      2ξℋₙ[ξ] - 2nℋₙ₋₁[ξ]
    # Shorthand Proof:
      ℋ↑
      𝔩↑ʼℊ(𝒟)↑ℊ
      𝔩ⁿ(-1)ʼℊ(𝒟)ⁿ𝒟ℊ
      𝔩ⁿ(-1)ʼℊ(𝒟)ⁿ[(-2ξ)ℊ]
      𝔩ⁿʼℊ(𝒟)ⁿ[2ξℊ]
      𝔩ⁿʼℊΣ[0,n]{m|(ⁿₘ)(𝒟)ᵐ[2ξ](𝒟)ⁿ⁻ᵐ[ℊ]}
      𝔩ⁿʼℊΣ[0,1]{m|(ⁿₘ)(𝒟)ᵐ[2ξ](𝒟)ⁿ⁻ᵐ[ℊ]}
      𝔩ⁿʼℊΣ{(ⁿ₀)(𝒟)⁰[2ξ](𝒟)ⁿ⁻⁰[ℊ],(ⁿ₁)(𝒟)¹[2ξ](𝒟)↓[ℊ]}
      𝔩ⁿʼℊ(2ξ(𝒟)ⁿ[ℊ] + 2n(𝒟)↓[ℊ])
      𝔩ⁿʼℊ2ξ(𝒟)ⁿ[ℊ] + 𝔩ⁿʼℊ2n(𝒟)↓[ℊ]
      2ξ𝔩ⁿʼℊ(𝒟)ⁿ[ℊ] + 2n𝔩ⁿʼℊ(𝒟)↓[ℊ]
      2ξ𝔩ⁿʼℊ(𝒟)ⁿ[ℊ] - 2n𝔩↓ʼℊ(𝒟)↓[ℊ]
      2ξℋ - 2nℋ↓
      2(ξℋ - nℋ↓)

    ℋ↑ = 2ℋ(ξ-↓n) = 2ξℋ - 2nℋ↓ = 2ξℋ - ŉ↓₂ℋ↓ = 2(ξℋ - ŉ↓ℋ↓)

###<a name="fqa"></a> ξℋ

    ξℋₙ[ξ] = ½ℋₙ₊₁[ξ] + nℋₙ₋₁[ξ]
    ξℋ = ½ℋ↑+nℋ↓   # Shorthand.
    # Proof:
      ℋₙ₊₁[ξ] = 2ξℋₙ[ξ] - 2nℋₙ₋₁[ξ]
      ℋₙ₊₁[ξ] + 2nℋₙ₋₁[ξ] = 2ξℋₙ[ξ]
      2ξℋₙ[ξ] = ℋₙ₊₁[ξ] + 2nℋₙ₋₁[ξ]
      ξℋₙ[ξ] = ½ℋₙ₊₁[ξ] + nℋₙ₋₁[ξ]
    # Shorthand Proof:
      ℋ↑ = 2ξℋ - 2nℋ↓
      ℋ↑+2nℋ↓ = 2ξℋ
      2ξℋ = ℋ↑+2nℋ↓
      ξℋ = ½(ℋ↑+2nℋ↓)
      ξℋ = ½ℋ↑+nℋ↓

    ξℋ = ℋ(↑½+↓n)   # Maybe?

    ξℋₙ[ξ]   = ½ℋₙ₊₁[ξ] + nℋₙ₋₁[ξ] = ½(ℋₙ↑[ξ] + ℋₙ↓[ξ]/(½n↧))

    # Shorthand.
    ξℋ = ½(ℋ↑+2nℋ↓) = ½(ℋ↑+ℋ↓/½n↧) = ½(ℋ↑+ℋ↓/n↧₂) = ½(ℋ↑+ŉ↧₂ℋ↓)

###<a name="rrF"></a> Ψₙ
Please accept the EigenState of the Simple Harmonic Oscillator Ψₙ
as given by Liboff's book in page 189.
The EigenState Ψₙ:

    Ψₙ[x] ≡ |ₙ⧽
    Ψₙ[x] = 𝐴ₙℋₙ[ξ]ℯ[-ξ²/2]

###<a name="W3A"></a> 𝒟 Ψ

    𝒟 Ψₙ = ½(√ŉ↧₂Ψₙ↓ - √n↥₂Ψₙ↑)
    # Proof:
      𝒟 Ψₙ
      𝒟 Ψ                                  # using shorthand
      𝒟[𝐴 ℋ 𝒢]
      𝐴(𝒟ℋ 𝒢 + ℋ 𝒟𝒢)                       # product rule
      𝐴(ŉ↧₂ℋ↓𝒢 - ξℋ𝒢)                      # 𝒢=-ξ𝒢
      𝐴𝒢(ŉ↧₂ℋ↓ - ξℋ)
      𝐴𝒢(ŉ↧₂ℋ↓ - ½(ℋ↑+ŉ↧₂ℋ↓))              # ξℋ=½(ℋ↑+ŉ↧₂ℋ↓)
      𝐴𝒢(ŉ↧₂ℋ↓ - ½ℋ↑ - ½ŉ↧₂ℋ↓)
      𝐴𝒢(½ŉ↧₂ℋ↓ - ½ℋ↑)
      ½𝐴𝒢(ŉ↧₂ℋ↓ - ℋ↑)
      ½𝐴𝒢(ŉ↧₂ℋ↓) - ½𝐴𝒢(ℋ↑)
      ½(√n↧₂𝐴↓)𝒢(ŉ↧₂ℋ↓) - ½(√n↥₂𝐴↑)𝒢(ℋ↑)   # 𝐴=√n↥₂𝐴↑=√n↧₂𝐴↓
      ½(𝐴↓)𝒢(√ŉ↧₂ℋ↓) - ½(√n↥₂𝐴↑)𝒢(ℋ↑)
      ½(√ŉ↧₂𝐴↓ℋ↓𝒢 - √n↥₂𝐴↑ℋ↑𝒢)             # Notice 𝒢 has no quantum number.
      ½(√ŉ↧₂Ψ↓ - √n↥₂Ψ↑)
      ½(√ŉ↧₂Ψₙ↓ - √n↥₂Ψₙ↑)                 # expand out context

    𝒟 Ψₙ = √½(√nΨₙ↓ - √[n+1]Ψₙ↑)
    # Proof:
      𝒟 Ψₙ
      ½(√ŉ↧₂Ψₙ↓ - √n↥₂Ψₙ↑)              # Just did this!
      ½(Ψₙ↓/√n↧₂ - √n↥₂Ψₙ↑)             # ŉ=1/n
      ½(Ψₙ↓/√n↧₂ - √[2(n+1)]Ψₙ↑)        # n↥₂=2(n+1)
      ½(Ψₙ↓/√[½(1/n)] - √[2(n+1)]Ψₙ↑)   # n↧₂=2⁻¹(1/n)
      ½(√2nΨₙ↓ - √[2(n+1)]Ψₙ↑)
      √½(√nΨₙ↓ - √[n+1]Ψₙ↑)             # ½√2=√½

    𝒟 Ψₙ = √½(√ŉ↧Ψₙ↓ - √n↥Ψₙ↑)   # ŉ↧=n,n↥=(n+1)
    𝒟 Ψ = √½(√ŉ↧Ψ↓-√n↥Ψ↑)

###<a name="e2c"></a> 𝑝𝒟 Ψ

    𝑝𝒟 Ψ = (ñ𝑝↓Ψ↓-n↥𝑝↑Ψ↑)/√2ñ
    # Proof:
      𝑝 √½(√ŉ↧Ψ↓-√n↥Ψ↑)
      √½(√ŉ↧𝑝Ψ↓-√n↥𝑝Ψ↑)
      # 𝑝=√[n↥/ñ]𝑝↑=√[ñn↧]𝑝↓
      √½(√ŉ↧√[ñn↧]𝑝↓Ψ↓-√n↥√[n↥/ñ]𝑝↑Ψ↑)
      (ñ𝑝↓Ψ↓-n↥𝑝↑Ψ↑)/√2ñ

###<a name="lHR"></a> Ψₒ

The State Function Ψₒ:

    Ψₒ[x] ≡ ΣΣ (𝑝ₙΨₙ[x])*(𝑝ₘΨₘ[x])
    Ψₒ[x] = Σ (𝑝ₙΨₙ[x])*(𝑝ₙΨₙ[x])   # Orthogonal normal states.
    Ψₒ[x] = Σ 𝑃ₙ Ψₙ[x]*Ψₙ[x]

    Ψₒ = Σ 𝑃 Ψ*Ψ   #  Shorthand.

> So this guy includes the distribution.

###<a name="quL"></a> ñ²=Σ{n²ΨₙΨₙ}
TODO: Need to prove this!

###<a name="4V4"></a> ξΨ
Motivation: I will be calculating ⧼Ψ|ξ|Ψ⧽ later.

    ξΨₙ = ½𝐴ₙ(ℋₙ₊₁[ξ] + 2nℋₙ₋₁[ξ])ℯ[-ξ²/2]
    ξΨ=½𝐴(ℋ↑+ŉ↧₂ℋ↓)𝒢   # Shorthand notation.
    # Proof:
      ξΨₙ                                # Given.
      ξ𝐴ₙℋₙ[ξ]ℯ[-ξ²/2]ℯ[-ξ²/2]           # Expansion of Ψₙ.
      ξ𝐴ℋ 𝒢                              # Shorthand.
      𝐴 ξℋ 𝒢                             # Rearrange.
      𝐴 ½(ℋ↑+ŉ↧₂ℋ↓)𝒢                     # ξℋ =½(ℋ↑+ŉ↧₂ℋ↓)
      ½𝐴(ℋ↑+ŉ↧₂ℋ↓)𝒢                      # Rearrage.
      ½𝐴ₙ(ℋₙ₊₁[ξ] + 2nℋₙ₋₁[ξ])ℯ[-ξ²/2]   # Expand expression.

    ξΨₙ = √½(√[n+1]Ψₙ₊₁ + √nΨₙ₋₁)
    ξΨ = ½(√n↥₂Ψ↑+√ŉ↧₂Ψ↓)   # Shorthand notation.
    # Proof:
      ξΨ
      ½𝐴(ℋ↑+ŉ↧₂ℋ↓)𝒢              # Previous result.
      ½𝐴ℋ↑𝒢 + ½𝐴ŉ↧₂ℋ↓𝒢           # Distribute all factors.
      ½𝐴ℋ↑𝒢 + ½ŉ↧₂𝐴ℋ↓𝒢           # Rearrange.
      ½𝐴ℋ↑𝒢 + ŉ↧𝐴ℋ↓𝒢             # ½(↧₂) is just ↧.
      ½√n↥₂𝐴↑ℋ↑𝒢 + ŉ↧√n↧₂𝐴↓ℋ↓𝒢   # 𝐴=√n↥₂𝐴↑=√n↧₂𝐴↓.
      ½√n↥₂𝐴↑ℋ↑𝒢 + ½ŉ↧₂√n↧₂𝐴↓ℋ↓𝒢 # ŉ↧=½ŉ↧₂.
      ½√n↥₂𝐴↑ℋ↑𝒢 + ½√ŉ↧₂𝐴↓ℋ↓𝒢    # ŉ↧₂√n↧₂=√ŉ↧₂.
      √½√n↥𝐴↑ℋ↑𝒢 + √½√ŉ↧𝐴↓ℋ↓𝒢    # ½(√↥₂) is √½(√↥).
      √½√n↥Ψ↑ + √½√ŉ↧Ψ↓          # Ψ is 𝐴ℋ𝒢.
      √½(√n↥Ψ↑ + √ŉ↧Ψ↓)          # Factor out √½.
      √½(√[n+1]Ψₙ₊₁ + √nΨₙ₋₁)    # Expand.

###<a name="1Wx"></a> ⧼ξ₀⧽
Evaluation of ⧼ξ₀⧽:

    ⧼ξ₀⧽ = ⧼Ψ₀|ξ|Ψ₀⧽             # 7.14a
    ⧼ξ₀⧽ = ⧼Ψ₀|n⧽⧼n|ξ|m⧽⧼m|Ψ₀⧽   # 7.14b

    ⧼ξ₀⧽ = ΣΣ (𝑝ₙΨₙ)* ξ (𝑝ₘΨₘ)
    ⧼ξ₀⧽ = ΣΣ Ψₙ*𝑝ₙ 𝑝ₘξΨₘ                                          # rearrange, 𝑝 is real.
    ⧼ξ₀⧽ = ΣΣ Ψₙ*𝑝ₙ 𝑝ₘ ½𝐴ₘ(ℋₘ↑[ξ] + ℋₘ↓[ξ]/(½m↓))                  # substitute for ξΨₘ
    ⧼ξ₀⧽ = ΣΣ Ψₙ*𝑝ₙ ½𝐴ₘ(𝑝ₘℋₘ↑[ξ] + 𝑝ₘℋₘ↓[ξ]/(½m↓))                 # distribute 𝑝ₘ
    ⧼ξ₀⧽ = ΣΣ{𝑝ₙΨₙ*𝑝ₙ ½𝐴ₘ𝑝ₘℋₘ↑[ξ]} + ΣΣ{Ψₙ*𝑝ₙ ½𝐴ₘ𝑝ₘℋₘ↓[ξ]/(½m↓)}   # separate
    ⧼ξ₀⧽ = ½ΣΣ{Ψₙ*𝑝ₙ 𝑝ₘ 𝐴ₘℋₘ↑[ξ]} + ½ΣΣ{Ψₙ*𝑝ₙ 𝑝ₘ 𝐴ₘℋₘ↓[ξ]/(½m↓)}   # take out ½
    # get the m's to match
    ⧼ξ₀⧽ = ½ΣΣ{Ψₙ*𝑝ₙ √m↑𝑝ₘ↑/√ñ √[2m↑]𝐴ₘ↑ℋₘ↑[ξ]} + ½ΣΣ{Ψₙ*𝑝ₙ √[ñm↓]𝑝ₘ↓ √[½m↓]𝐴ₘ↓ℋₘ↓[ξ]/(½m↓)}
    ⧼ξ₀⧽ = 1/√2ñΣΣ{Ψₙ*𝑝ₙ m↑𝑝ₘ↑𝐴ₘ↑ℋₘ↑[ξ]} + √½ñΣΣ{Ψₙ*𝑝ₙ 𝑝ₘ↓𝐴ₘ↓ℋₘ↓[ξ]}
    ⧼ξ₀⧽ = 1/√2ñΣΣ{Ψₙ*𝑝ₙ m↑ 𝑝ₘ↑Ψₘ↑} + √½ñΣΣ{Ψₙ*𝑝ₙ 𝑝ₘ↓Ψₘ↓}
    ⧼ξ₀⧽ = 1/√2ñΣ{Ψₙ*𝑝ₙ n 𝑝ₙΨₙ} + √½ñΣ{Ψₙ*𝑝ₙ𝑝ₙΨₙ}           # Orthogonal states
    ⧼ξ₀⧽ = 1/√2ñΣΣ{n𝑃ₙ} + √½ñΣ{𝑃ₙ}                          # Ψₙ*Ψₙ=1, 𝑝ₙ𝑝ₙ=𝑃ₙ
    ⧼ξ₀⧽ = 1/√2ñ ñ + √½ñ
    ⧼ξ₀⧽ = √½ñ + √½ñ
    ⧼ξ₀⧽ = 2√½ñ
    ⧼ξ₀⧽ = √2ñ
    ⧼ξ₀⧽² = 2ñ   # OK, need time development

###<a name="jiD"></a> ⌽𝐴ℋ↓/½n↓=⌽↥/√½n↓⌽↓Ψ↓

    ⌽𝐴ℋ↓/½n↓
    ⌽√[½n↓]𝐴↓ℋ↓/½n↓   # 𝐴=√[½n↓]𝐴↓
    ⌽𝐴↓ℋ↓/√[½n↓]
    ⌽↥⌽↓𝐴↓ℋ↓/√½n↓     # ⌽=⌽₁⌽↓
    ⌽↥/√½n↓ ⌽↓𝐴↓ℋ↓
    ⌽↥/√½n↓ ⌽↓Ψ↓

###<a name="5Mz"></a> ⌽𝐴ℋ↑=⌽↧√2n↑⌽↑Ψ↑

    ⌽𝐴ℋ↑
    ⌽√2n↑𝐴↑ℋ↑   # 𝐴=√[2n↑]𝐴↑
    ⌽↧⌽↑√2n↑𝐴↑ℋ↑
    ⌽↧⌽↑√2n↑𝐴↑ℋ↑
    ⌽↧√2n↑ ⌽↑𝐴↑ℋ↑
    ⌽↧√2n↑ ⌽↑Ψ↑

###<a name="V1C"></a> 𝑝↑𝑝=√[ñ/n↑]𝑃

    𝑝↑𝑝
    √[ñⁿ⁺¹ℯ[-ñ]/(n+1)!] 𝑝
    √[ñ/(n+1) ñⁿℯ[-ñ]/n!] 𝑝
    √[ñ/(n+1)]𝑝 𝑝
    √[ñ/(n+1)]𝑃
    √[ñ/n₁]𝑃
    √[ñ/n↑]𝑃

###<a name="AyD"></a> 𝑝↓𝑝=𝑃/√[n↓ñ]

   𝑝↓𝑝
    √[ñⁿ⁻¹ℯ[-ñ]/(n-1)!] 𝑝
    √[(n/ñ) ñℯ[-ñ]/n!] 𝑝
    √[n/ñ] 𝑝 𝑝
    √[1/(n₋₁ñ)]𝑃
    𝑃/√[n₋₁ñ]
    𝑃/√[n↓ñ]

###<a name="geS"></a> ⧼ξₜ⧽
Evaluation of ⧼ξₜ⧽:

    ⧼ξₜ⧽ = ⧼Ψ|ξ|Ψ⧽
    ⧼ξₜ⧽ = ⧼Ψ|n⧽⧼n|ξ|m⧽⧼m|Ψ⧽
    ⧼ξₜ⧽ = ΣΣ (𝑝ₙ⌽ᵗₙΨₙ)* ξ (𝑝ₘ⌽ᵗₘΨₘ)
    # Parralles ⧼ξ₀⧽ up to the here...
    ⧼ξₜ⧽ = ½ΣΣ{(⌽ᵗₙΨₙ)*𝑝ₙ 𝑝ₘ ⌽ᵗₘ𝐴ₘℋₘ↑[ξ]} + ½ΣΣ{⌽ᵗₙΨₙ*𝑝ₙ 𝑝ₘ ⌽ᵗₘ𝐴ₘℋₘ↓[ξ]/(½m↓)}
    ⧼ξₜ⧽ = ½(Σ{(⌽Ψ)*𝑝}Σ{𝑝⌽𝐴ℋ↑[ξ]} + Σ{(⌽Ψ)*𝑝}Σ{𝑝⌽𝐴ℋ↓[ξ]/½n↓})            # ΣΣ{αₙβₘ}=Σ{αₙ}Σ{βₙ}, context indeces.
    ⧼ξₜ⧽ = ½(Σ{(⌽↑Ψ↑)*𝑝↑}Σ{𝑝⌽↧√2n↑⌽↑Ψ↑} + Σ{(⌽↓Ψ↓)*𝑝↓}Σ{𝑝⌽↥/√½n↓⌽↓Ψ↓})   # TODO: What am I doing here???
    ⧼ξₜ⧽ = ½(Σ{(⌽↑Ψ↑)*𝑝↑𝑝⌽↧√2n↑⌽↑Ψ↑} + Σ{(⌽↓Ψ↓)*𝑝↓𝑝⌽↥/√½n↓⌽↓Ψ↓})         # Orthogonal states
    ⧼ξₜ⧽ = ½(Σ{𝑝↑𝑝⌽↧√2n↑} + Σ{𝑝↓𝑝⌽↥/√½n↓})                               # Normalized states, Ψ*Ψ=1
    ⧼ξₜ⧽ = ½(Σ{√[ñ/n↑]𝑃⌽↧√2n↑} + Σ{𝑃⌽↥/√[n↓ñ]/√½n↓})
    ⧼ξₜ⧽ = ½(Σ{√ñ𝑃⌽↧√2} + Σ{𝑃⌽↥/√½ñ/n↓})
    ⧼ξₜ⧽ = ½(Σ{√ñ𝑃⌽↧√2} + Σ{𝑃n⌽↥/√½ñ})
    ⧼ξₜ⧽ = ½(Σ{√2ñ𝑃⌽↧} + Σ{𝑃n⌽↥/√½ñ})
    ⧼ξₜ⧽ = ½(√2ñ⌽↧Σ{𝑃} + ⌽↥/√½ñΣ{𝑃n})
    ⧼ξₜ⧽ = ½(√2ñ⌽↧Σ{𝑃} + ⌽↥√2ñ)
    ⧼ξₜ⧽ = ½(√2ñ⌽↧ + ⌽↥√2ñ)
    ⧼ξₜ⧽ = ½√2ñ(⌽↧ + ⌽↥)
    ⧼ξₜ⧽ = ½√2ñ(2c₁)
    ⧼ξₜ⧽ = √2ñ c₁
    ⧼ξₜ⧽² = 2ñ c₁
    ⧼ξₜ⧽² = 2ñ:Cosine²[nwt]
    # This time I got Cosine... Why?  Not careful enough with φ↥ and φ↧?

###<a name="WaV"></a> ⧼ξ²⧽
TODO: ⧼ξ²⧽:

    ⧼ξ²⧽ = (ñ+½) + ½Σ ⌽ₙ*𝑝ₙ* (⌽ₙ₋₂√[n(n-1)]𝑝ₙ₋₂ +  ⌽ₙ₊₂√[(n+1)(n+2)]𝑝ₙ₊₂)   # 7.21
    # And much nicer...
    ⧼ξ²⧽ = (ñ+½) + ½Σ ⌽*𝑝 (⌽↓²/√n↓² 𝑝↓² +  ⌽↑²√n↑² 𝑝↑²)         # pretty noted
    ⧼ξ²⧽ = (ñ+½) + ½Σ ⌽*⌽↓²/√n↓² 𝑝𝑝↓² +  ⌽*⌽↑²√n↑² 𝑝𝑝↑²         # Distribute
    ⧼ξ²⧽ = (ñ+½) + ½Σ φ↧²/√n↓² 𝑝𝑝↓² +  φ↥²√n↑² 𝑝𝑝↑²           # ⌽→φ
    ⧼ξ²⧽ = (ñ+½) + ½Σ φ↧²/√n↓² 𝑃/(ñ√n↓²) +  φ↥²√n↑² ñ𝑃/√n↑²   # 𝑝->𝑃
    ⧼ξ²⧽ = (ñ+½) + ½Σ φ↧²/n↓² 𝑃/ñ +  φ↥² ñ𝑃                # Simplify
    ⧼ξ²⧽ = (ñ+½) + ½Σ φ↧² n(n-1) 𝑃/ñ +  φ↥² ñ𝑃            # 1/n↓² = n(n-1)
    ⧼ξ²⧽ = (ñ+½) + ½(Σ{φ↧² n(n-1) 𝑃/ñ} +  Σ{φ↥² ñ𝑃})      # Separate sums
    ⧼ξ²⧽ = (ñ+½) + ½(φ↧²/ñΣ{n(n-1)𝑃} +  φ↥²ñΣ{𝑃})         # Take out the constants
    ⧼ξ²⧽ = (ñ+½) + ½(φ↧²/ñ(ñ²) +  φ↥²ñ(1))                # Evaluate sums
    ⧼ξ²⧽ = (ñ+½) + ½(φ↧²ñ + φ↥²ñ)                         # Simplify
    ⧼ξ²⧽ = (ñ+½) + ½ñ(φ↧² + φ↥²)
    ⧼ξ²⧽ = (ñ+½) + ½ñ(2c₂)                                # Remember?  φ↧²+φ↥²=2c₂.
    ⧼ξ²⧽ = (ñ+½) + ñc₂
    ⧼ξ²⧽ = (ñ+½) + ñ(1-2s²₁)                              # Double angle, c₂=1-2s²₁
    ⧼ξ²⧽ = (ñ+½) + ñ- 2ñs²₁
    ⧼ξ²⧽ = 2ñ + ½ - 2ñs²₁
    ⧼ξ²⧽ = ½ + 2ñ - 2ñs²₁
    ⧼ξ²⧽ = ½ + 2ñ(1 - s²₁)
    ⧼ξ²⧽ = ½ + 2ñc²₁                                      # Pythagoras
    ⧼ξ²⧽ = ½ + 2ñ:Cosine²[nwt]

###<a name="8NW"></a> Δ²ξ
7.5 Results:

    Δ²ξ = ⧼ξ²⧽ - ⧼ξ⧽²
        = (½ + 2ñc²₁) - 2ñc²₁
        = ½

##<a name="1Pu"></a> Optimization problem
The [Optimization problem](http://en.wikipedia.org/wiki/Optimization_problem)
to be solved:

    :Minimize:   Δ𝐱Δ𝐩
    :Subject_to: ⧼Ψₒ|𝐇|Ψₒ⧽ = Eₒ

This will be for the quantum mechanical simple harmonic oscillator
with energy [Eₒ](SCRATCH.md#k5Y),
state function [Ψₒ](SCRATCH.md#lHR),
Hamiltonian(energy) operator [𝐇](SCRATCH.md#bdY),
position operator [𝐱](SCRATCH.md#0bH), and
momentum operator [𝐩](SCRATCH.md#w6M).
I will show that the product of the variance of position [Δ²x](SCRATCH.md#oY8)
and momentum [Δ²p](SCRATCH.md#k94) is the minimum when the state Ψₒ
is composed of a Poisson distribution [𝑃ₙ](SCRATCH.md#o0H) of energy states, and
that the minimum is that set by the uncertainty principle
due to the commutator relationship between 𝐱 and 𝐩, [&#91;𝐱,𝐩&#93;](SCRATCH.md#bST).

> TODO: section on quantum number n.

Noting that [Eₙ](SCRATCH.md#2Xh) goes as the quantum number n, and
using the definitions of Δ𝐱 and Δ𝐩, I then have:

    :Minimize:   √ (⧼𝐱²⧽-⧼𝐱⧽²)(⧼𝐩²⧽-⧼𝐩⧽²)
    :Subject_to: ⧼n⧽ = ñ

where [ñ](SCRATCH.md#Ojo) is the average quantum number.

###<a name="i9c"></a> symmetries?
It would not be to hard to argue (TODO: demonstrate this) that
by symmetry (⧼𝐱²⧽-⧼𝐱⧽²)=(⧼𝐩²⧽-⧼𝐩⧽²) and also that I can set ⧼𝐱⧽=0.
Then the problem is:

    :Minimize:   ⧼𝐱²⧽
    :Subject_to: ⧼n⧽=ñ, ⧼𝐱⧽=0, ⧼𝐱²⧽=⧼𝐩²⧽-⧼𝐩⧽²

> So here I actually mean the non-dimensional versions, right?

I suspect the extra conditions might be satisfied "for free".
Let's see how that goes:

    :Min: ⧼𝐱²⧽
    :Sub: ⧼n⧽ = ñ   # Ignoring the rest of the constraints for now.

###<a name="ij2"></a> ℒ
[Lagrange multiplier](http://en.wikipedia.org/wiki/Lagrange_multiplier):

    ℒ := ⧼𝐱²⧽ + ℝ{λ}(⧼n⧽-ñ)   # Let ℒ be... := is just a weaker form of ≡.

    𝒟ₓℒ = 𝒟ₓ⧼𝐱²⧽ + λ𝒟ₓ⧼n⧽ - λ𝒟ₓñ
    𝒟ₓℒ = 𝒟ₓ⧼𝐱²⧽ + λ𝒟ₓ⧼n⧽   # ñ is just a constant and goes away.

𝒟ₓ is the derivative with respect to x.
I will also use [𝒟](SCRATCH.md#8P4)
as the derivative with respect to [ξ](SCRATCH.md#Pvg),
the non-dimensional displacement.

###<a name="Jbc"></a> 𝒟 ⧼n⧽=0
Consider ⧼n⧽.
Just want to prove ⧼n⧽ really is a simple constant.

    𝒟ₓ⧼n⧽
    𝒟 ⧼n⧽                   # Change of variable, ξ.
    𝒟 ⧼Ψₒ|ₙ⧽⧼ₙ|n|ₘ⧽⧼ₘ|Ψₒ⧽   # Expanding out ⧼n⧽.

I will use [⨋](SCRATCH.md#AXS) to denote an an integral over ξ of a sum over n and m.

    𝒟 ⧼Ψₒ|ₙ⧽⧼ₙ|n|ₘ⧽⧼ₘ|Ψₒ⧽       # Continue from above.
    𝒟 ⨋ (𝑝ₙΨₙ)*n𝑝ₘΨₘ            # ⨋ is an integral over ξ of a sum over n and m!
    𝒟 ⨋ (𝑝Ψ*)n𝑝ₘΨₘ              # Context ₙ for brevity.
    𝒟 ⨋ 𝑝*Ψn𝑝ₘΨₘ                # There is nothing to conjugate in Ψₙ.
    𝒟 ⨋ n𝑝*𝑝ₘΨΨₘ                # Rearrangement.
    𝒟 ⨋ n𝒫ΨΨₘ                   # 𝒫ₙₘ=𝑝*𝑝ₘ, context n and m.
    ⨋ n𝒫𝒟[ΨΨₘ]                  # 𝒟 only acts on Ψ.
    ⨋ n𝒫(𝒟[Ψ]Ψₘ + Ψ𝒟[Ψₘ])       # Product rule.
    ⨋{n𝒫𝒟[Ψ]Ψₘ} + ⨋{n𝒫Ψ𝒟[Ψₘ]}   # Separate sums.

Note that although [𝒫](SCRATCH.md#IRG) is [ℝ](SCRATCH.md#yfS),
[𝑝](SCRATCH.md#2on) might be [ℂ](SCRATCH.md#Ama).
See the derivation of [𝒟 Ψ](SCRATCH.md#W3A).
Then proceed:

    ⨋{n𝒫𝒟[Ψ]Ψₘ} + ⨋{n𝒫Ψ𝒟[Ψₘ]}                               # Continue from above.
    ⨋{n𝒫(√½(√ŉ↧Ψ↓-√n↥Ψ↑))Ψₘ} + ⨋{n𝒫Ψ(√½(√ʼm↧Ψₘ↓-√m↥Ψₘ↑))}   # Subtitution of 𝒟 Ψ.
    √½(⨋{n𝒫(√ŉ↧Ψ↓-√n↥Ψ↑)Ψₘ} + ⨋{n𝒫Ψ(√ʼm↧Ψₘ↓-√m↥Ψₘ↑)})       # Take out √½.

That 𝒟 ⧼n⧽ vanishes should not be a property of 𝑝 (in 𝒫).
I proceed as if I don't know what 𝑝 is:

    √½(⨋{n𝒫(√ŉ↧Ψ↓-√n↥Ψ↑)Ψₘ} + ⨋{n𝒫Ψ(√ʼm↧Ψₘ↓-√m↥Ψₘ↑)})       # Continue from above.
    √½(⨋{n𝒫(√ŉ↧Ψ↓Ψₘ-√n↥Ψ↑Ψₘ)} + ⨋{n𝒫(√ʼm↧ΨΨₘ↓-√m↥ΨΨₘ↑)})    # Distribute Ψ.
    √½(⨋{n𝒫√ŉ↧Ψ↓Ψₘ-n𝒫√n↥Ψ↑Ψₘ} + ⨋{n𝒫√ʼm↧ΨΨₘ↓-n𝒫√m↥ΨΨₘ↑})    # Distribute n𝒫.
    √½(⨋{n√ŉ↧𝒫Ψ↓Ψₘ-n√n↥𝒫Ψ↑Ψₘ} + ⨋{n√ʼm↧𝒫ΨΨₘ↓-n√m↥𝒫ΨΨₘ↑})    # Rearrangement.
    √½(⨋{n√n𝒫Ψ↓Ψₘ-n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓-n√[m+1]𝒫ΨΨₘ↑})   # Evaluate "factorals".

There are positive and negative terms very much like eachother.
Going to match them up.
I will be using [𝛿](SCRATCH.md#VuP) as the Dirac delta function:

    √½(⨋{n√n𝒫Ψ↓Ψₘ-n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓-n√[m+1]𝒫ΨΨₘ↑})       # Continue from above.
    √½(⨋{n√n𝒫Ψ↓Ψₘ}-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓}-⨋{n√[m+1]𝒫ΨΨₘ↑}) # Separate sums.
    √½(⨋{n√n𝒫Ψ↓Ψₘ}-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓}-⨋{n√m𝒫↓ΨΨₘ})     # ↓ m, 4th ⨋.
    √½(⨋{n√n𝒫Ψ↓Ψₘ}-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓}-⨋{n√n𝒫↓𝛿})       # ⟂ΨΨ=𝛿, 4th ⨋.
    √½(⨋{n√n𝒫↓Ψ↓Ψₘ↓}-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓}-⨋{n√n𝒫↓𝛿})     # ↓ m, 1st ⨋.
    √½(⨋{n√n𝒫↓𝛿}-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓}-⨋{n√n𝒫↓𝛿})         # ⟂ΨΨ=𝛿, 1st ⨋.
    √½(-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√m𝒫ΨΨₘ↓})                            # Cancellation.
    √½(-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√[m+1]𝒫↑ΨΨₘ})                        # ↑ m, 2nd ⨋.
    √½(-⨋{n√[n+1]𝒫Ψ↑Ψₘ}+⨋{n√[n+1]𝒫↑𝛿})                          # ⟂ΨΨ=𝛿, 2nd ⨋.
    √½(-⨋{n√[n+1]𝒫↑Ψ↑Ψₘ↑}+⨋{n√[n+1]𝒫↑𝛿})                        # ↑ m, 1st ⨋.
    √½(-⨋{n√[n+1]𝒫↑𝛿}+⨋{n√[n+1]𝒫↑𝛿})                            # ⟂ΨΨ=𝛿, 1st ⨋.
    0                                                           # Cancellation.

I should point out that these are sums over Integers,
not just natural numbers.
But there are no negative quantum numbers for the harmonic oscillator.
That is, for quantum numbers less than 0, the states are zero!
So there are no dangling terms with [∑u↑](SCRATCH.md#Uf9) or [∑u↓](SCRATCH.md#blg).

###<a name="iFR"></a> 𝒟ₓ⧼𝐱²⧽
Consider ⧼𝐱²⧽.
This should give the properties of an optimun distribution:

    𝒟ₓ⧼𝐱²⧽
    𝒟ₓ⧼x²⧽                        # x is the position operator.
    𝒟ₓ⧼ξ²⧽                        # Change of variable, dimensionless ξ.
    𝒟ₓ ⧼Ψₒ|ₙ⧽⧼ₙ|ξ²|ₘ⧽⧼ₘ|Ψₒ⧽       # Expanding out ⧼ξ²⧽.
    𝒟 ⨋ (𝑝ₙΨₙ)*ξ²𝑝ₘΨₘ             # ⨋ is an integral over ξ of a sum over n and m!
    𝒟 ⨋ (𝑝Ψ)*ξ²𝑝ₘΨₘ               # Implicit n, explicit m.
    𝒟 ⨋ 𝑝Ψξ²𝑝ₘΨₘ                  # Nothing to conjugate.
    𝒟 ⨋ 𝑝𝑝ₘξ²ΨΨₘ                  # Rearrange.
    𝒟 ⨋ 𝑝𝑝ₘξΨξΨₘ                  # Pair up ξΨ.
    ⨋ 𝑝𝑝ₘ𝒟[ξΨξΨₘ]                 # 𝒟 only acts on ξΨ.
    ⨋ 𝑝𝑝ₘ𝒟[(ξΨ)(ξΨₘ)]             # Going to apply product rule this way.
    ⨋ 𝑝𝑝ₘ(𝒟[ξΨ]ξΨₘ+ξΨ𝒟[ξΨₘ])      # Product rule.
    ⨋ 𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ+𝑝𝑝ₘξΨ𝒟[ξΨₘ]     # Distribute 𝑝𝑝ₘ.
    ⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ}+⨋{𝑝𝑝ₘξΨ𝒟[ξΨₘ]} # Separate sums.
    ⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ}+⨋{𝑝ₘ𝑝ξΨₘ𝒟[ξΨ]} # Switch n and m in 2nd ⨋.
    ⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ}+⨋{𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ} # Rearange.
    2⨋ 𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ                # The two ⨋s are the same.

See the derivation of [ξΨ](SCRATCH.md#4V4). Then proceed:

    2⨋ 𝑝𝑝ₘ𝒟[ξΨ]ξΨₘ                # Continue from above.
    2⨋ 𝑝𝑝ₘ(𝒟[ξ]Ψ+ξ𝒟[Ψ])ξΨₘ        # Product rule.
    2⨋ 𝑝𝑝ₘ(Ψ+ξ𝒟[Ψ])ξΨₘ            # 𝒟 ξ = 1.
    2⨋ 𝑝𝑝ₘ(ΨξΨₘ+ξ𝒟[Ψ]ξΨₘ)         # Distribute ξΨₘ.
    2⨋ 𝑝𝑝ₘΨξΨₘ+𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ        # Distribute 𝑝𝑝ₘ.
    2⨋{𝑝𝑝ₘΨξΨₘ}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}   # Separate sums.
    2⨋{ξ𝑝𝑝ₘΨΨₘ}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}   # Rearrage in 1st ⨋.
    2⨋{ξ𝑝𝑝ₘ𝛿}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}     # ⟂ΨΨ=𝛿.
    2∫{⅀{ξ𝑝𝑝ₘ𝛿}}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}  # Wuts really goin on in 1st ⨋.
    2∫{ξ⅀{𝑝𝑝ₘ𝛿}}+2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}  # Take ξ out off ⅀(sum over n and m).
    2∫{ξ∑𝑃} + 2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}     # ⅀ 𝑝𝑝ₘ𝛿 = ∑𝑃
    2∫{ξ} + 2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}       # Sum of a distribution, ∑𝑃 = 1.
    2⨋{𝑝𝑝ₘξ𝒟[Ψ]ξΨₘ}               # ∫ξ=0
    2⨋{𝑝𝑝ₘξ(√½(√ŉ↧Ψ↓-√n↥Ψ↑))ξΨₘ}  # Substitute in 𝒟 Ψ.
    √2⨋{𝑝𝑝ₘξ(√ŉ↧Ψ↓-√n↥Ψ↑)ξΨₘ}     # √½(2)=√2
    √2⨋{(√ŉ↧ξ𝑝Ψ↓-√n↥ξ𝑝Ψ↑)ξ𝑝ₘΨₘ}   # Pair up ξ𝑝Ψ(distribute).
    √2⨋{(√ŉ↧ξ𝑝Ψ↓ξ𝑝ₘΨₘ-√n↥ξ𝑝Ψ↑ξ𝑝ₘΨₘ)}
    √2(⨋{(√ŉ↧ξ𝑝Ψ↓ξ𝑝ₘΨₘ}-⨋{√n↥ξ𝑝Ψ↑ξ𝑝ₘΨₘ)})
    √2(⨋{(√ŉ↧ξ²𝑝Ψ↓𝑝ₘΨₘ}-⨋{√n↥ξ²𝑝Ψ↑𝑝ₘΨₘ)})
    √2(⨋{(ξ²√ŉ↧𝑝Ψ↓𝑝ₘΨₘ}-⨋{ξ²√n↥𝑝Ψ↑𝑝ₘΨₘ)})
    √2(⨋{ξ²√ŉ↧√[ñn↧]𝑝↓Ψ↓𝑝ₘΨₘ}-⨋{ξ²√n↥√[ʼñn↥]𝑝↑Ψ↑𝑝ₘΨₘ}) # 𝑝 = √(m,ʼñ)↥𝑝↑ = √(m,ʼñ)↧𝑝↓
    √2(⨋{ξ²ŉ↧√ñ𝑝↓Ψ↓𝑝ₘΨₘ}-⨋{ξ²n↥√ʼñ𝑝↑Ψ↑𝑝ₘΨₘ})
    √2(⨋{ξ²ŉ↧√ñ𝑝↓Ψ↓𝑝↓Ψ↓}-⨋{ξ²n↥√ʼñ𝑝↑Ψ↑𝑝↑Ψ↑})   # Set m to match.
    √2(⨋{ξ²ŉ↧√ñ𝑃↓𝛿}-⨋{ξ²n↥√ʼñ𝑃↑𝛿})
    √2(⨋{ξ²n√ñ𝑃↓𝛿}-⨋{ξ²(n+1)√ʼñ𝑃↑𝛿})   # Evaluate "factorals"

    n√ñ𝑃↓ = (n+1)√ʼñ𝑃↑  # B.4 ???
    n√ñ𝑃↓ = (n+1)𝑃↑/√ñ
    n√ñ𝑃 = (n+1)𝑃↑²/√ñ
    n√ñ𝑃 = (n+1)𝑃ₙ₊₂/√ñ
    n𝑃 = (n+1)𝑃ₙ₊₂/ñ
    𝑃 = (n+1)𝑃ₙ₊₂/(nñ)
    ñ𝑃 = (n+1)𝑃ₙ₊₂/n

> WOW! OK, I think I now understand what I did 25 years ago.
> I need to follow the original thesis more closely!  LOL.

###<a name="3nH"></a> ⧼u⧽ₜ

    ⧼u⧽ₜ ≡ ⧼⌽ᵗΨₒ|n⧽⧼n|u|m⧽⧼m|⌽ᵗΨₒ⧽

###<a name="y2B"></a> Ψₒₜ
TODO

###<a name="p3u"></a> ⌽↑

    ⌽↑ = ⌽φ₁ = ⌽φ↥   # Shorthand
    ⌽ᵗₙ↑ = ⌽ᵗₙφᵗ₁
    # Proof:
      ⌽ᵗₙ↑
      ⌽ᵗₙ₊₁
      ℯ[-𝑖ω((n+1)+½)t]
      ℯ[-𝑖ωt(n+½+1)]
      ℯ[-𝑖ωt(n+½)+(-𝑖ωt)]
      ℯ[-𝑖ωt(n+½)]ℯ[-𝑖ωt]
      ⌽ᵗₙℯ[-𝑖ωt]
      ⌽ᵗₙφᵗ₁
      ⌽ₙφ₁
      ⌽φ₁
      ⌽φ↥

###<a name="BNu"></a> ⌽↓

    ⌽↓ = ⌽φ₋₁ = ⌽φ↧   # Likewise as ⌽↑.


###<a name="2q7"></a> ⌽↑,⌽↓

    ⌽ = ⌽↓/φ↧ = φ↥⌽↓
    ⌽ = ⌽↑/φ↥ = φ↧⌽↑
    # Proof:
      φ↥
      ℯ[-𝑖ωt]
      ℯ[-1(𝑖ωt)]
      (ℯ[𝑖ωt])⁻¹
      (ℯ[-1(-𝑖ωt)])⁻¹
      (φ↧)⁻¹
      1/φ↧
      ʼφ↧

###<a name="g9G"></a> 𝛿↓

> TODO: This is the delta function, 𝛿[n,m-1].

###<a name="QlY"></a> 𝛿↑

> TODO: This is the delta function, 𝛿[n,m+1].

##<a name="Nde"></a> ⧼𝐱⧽

    ⧼𝐱⧽
    ⧼x⧽                 # 𝐱 is just x.
    ⧼Ψₒ|ₙ⧽⧼ₙ|x|ₘ⧽⧼ₘ|Ψₒ⧽ # Expand out expression.
    ⨋ₓ(𝑝ₙΨₙ)*x(𝑝ₘΨₘ)    # Switched from ⧼⧽ to ⨋ₓ notation.
    ⨋ₓ𝒫ₙₘΨₙ*xΨₘ         # 𝒫ₙₘ = 𝑝ₙ*𝑝ₘ
    ⨋ₓ𝒫 Ψ*xΨₘ           # Implicit n, explicit m.
    ⨋ₓ𝒫 Ψ*√𝒽ξΨₘ         # Change of variable, x to ξ.
    √𝒽⨋ 𝒫 Ψ*ξΨₘ         # Take √𝒽 outside.

The [𝒽](SCRATCH.md#hIf) is there because x=√𝒽ξ, a shorthand to ℏ/(μω).
It's just a constant.

    √𝒽⨋ 𝒫 Ψ*ξΨₘ                  # Continue from above.
    √𝒽⨋ 𝒫 (ξΨ)*Ψₘ                # Rearrange, want ξΨ.
    √𝒽⨋ 𝒫 √½(√n↥Ψ↑+√ŉ↧Ψ↓)*Ψₘ     # Subtitute for ξΨ.
    √½𝒽⨋ 𝒫 (√n↥Ψ↑+√ŉ↧Ψ↓)*Ψₘ      # Factor out the √½.
    √½𝒽⨋ 𝒫 (√n↥Ψ↑*Ψₘ+√ŉ↧Ψ↓*Ψₘ)   # Distribute Ψₘ.
    √½𝒽⅀ 𝒫 (√n↥𝛿↑+√ŉ↧𝛿↓)
    √½𝒽⅀ 𝑝*𝑝ₘ(√n↥𝛿↑+√ŉ↧𝛿↓)       # 𝑝*𝑝ₘ = 𝒫 .
    √½𝒽⅀ 𝑝*(√n↥𝑝ₘ𝛿↑+√ŉ↧𝑝ₘ𝛿↓)     # Distribute 𝑝ₘ.
    √½𝒽⅀ 𝑝*(√n↥𝑝ₘ↑𝛿+√ŉ↧𝑝ₘ↓𝛿)
    √½𝒽∑ 𝑝*(√n↥𝑝↑+√ŉ↧𝑝↓)
    √½𝒽∑ 𝑝*(√[n+1]𝑝↑+√n𝑝↓)       # Evaluate "factorals".
    √½𝒽∑ 𝑝ₙ*(√[n+1]𝑝ₙ₊₁+√n𝑝ₙ₋₁)  # Explicit n.

> TODO: Need to explain how 𝛿↑ and 𝛿↓ work.

    ⧼𝐱⧽ = √[½ℏ/(μω)] ∑ {𝑝ₙ*(√[n+1]𝑝ₙ₊₁ + √[n]𝑝ₙ₋₁)}

    √½𝒽(∑{√[n+1]𝑝ₙ*𝑝ₙ₊₁} + ∑{√[n]𝑝ₙ*𝑝ₙ₋₁})
    √½𝒽(∑{√[n+1]𝒫↑} + ∑{√[n+1]𝒫↑*})

###<a name="1o3"></a> ⧼𝐱⧽²

    ⧼𝐱⧽²
    (√[½ℏ/(μω)] ∑ {𝑝ₙ*(√[n+1]𝑝ₙ₊₁ + √[n]𝑝ₙ₋₁)})²
    (√½𝒽∑{√[n+1]𝒫↑+√n𝒫↓})²   # Shorthand
    ½𝒽∑²{√[n+1]𝒫↑+√n𝒫↓}

###<a name="GJG"></a> ⧼ξ⧽

    ⧼ξ⧽
    ⧼x/√𝒽⧽   # x=√𝒽ξ
    1/√𝒽⧼x⧽
    1/√𝒽 √½𝒽∑ 𝑝ₙ*(√[n+1]𝑝ₙ₊₁+√n𝑝ₙ₋₁)
    √½∑ 𝑝ₙ*(√[n+1]𝑝ₙ₊₁+√n𝑝ₙ₋₁)

>  This is equation [7.15](Y.md).

##<a name="B0z"></a> ⧼𝐱²⧽

    ⧼𝐱²⧽
    ⧼x²⧽                 # 𝐱 is just x.
    ⧼Ψₒ|ₙ⧽⧼ₙ|x²|ₘ⧽⧼ₘ|Ψₒ⧽ # Expand out expression.
    ⨋ₓ (𝑝ₙΨₙ)*x²(𝑝ₘΨₘ)   # Switched from ⧼⧽ to ⨋ₓ notation.
    ⨋ₓ 𝒫ₙₘΨₙ*x²Ψₘ        # 𝒫ₙₘ = 𝑝ₙ*𝑝ₘ
    ⨋ₓ 𝒫 Ψ*x²Ψₘ          # Implicit n, explicit m.
    ⨋ₓ 𝒫 Ψ*𝒽ξ²Ψₘ         # Change of variable, x to ξ.
    𝒽⨋ 𝒫 Ψ*ξ²Ψₘ          # Take 𝒽 outside.

The [𝒽](SCRATCH.md#hIf) is there because x=√𝒽ξ, a shorthand to ℏ/(μω).
It's just a constant.

    𝒽⨋ 𝒫 Ψ*ξ²Ψₘ   # Continue from above.
    𝒽⨋ 𝒫 Ψ*ξξΨₘ
    𝒽⨋ 𝒫 ξΨ*ξΨₘ
    𝒽⨋ 𝒫 √½(√n↥Ψ↑+√ŉ↧Ψ↓)*ξΨₘ
    𝒽⨋ 𝒫 √½(√n↥Ψ↑+√ŉ↧Ψ↓)*√½(√m↥Ψₘ↑+√ʼm↧Ψₘ↓)
    ½𝒽⨋ 𝒫 (√n↥Ψ↑+√ŉ↧Ψ↓)*(√m↥Ψₘ↑+√ʼm↧Ψₘ↓)
    ½𝒽⨋ 𝒫 (√n↥Ψ↑*√m↥Ψₘ↑ + √n↥Ψ↑*√ʼm↧Ψₘ↓ + √ŉ↧Ψ↓*√m↥Ψₘ↑ + √ŉ↧Ψ↓*√ʼm↧Ψₘ↓)
    ½𝒽⅀ 𝒫 (n↥𝛿 + √n↥√ʼm↧𝛿↑↓ + √ŉ↧√m↥𝛿↓↑ + ŉ↧𝛿)

> TODO: Need to explain 𝛿↓↑.
> 𝛿↑↓ means when n+1=m-1, 𝛿↓↑ means when n-1=m+1.

    ½𝒽⅀ 𝒫 (n↥𝛿 + √n↥√ʼm↧𝛿↑↓ + √ŉ↧√m↥𝛿↓↑ + ŉ↧𝛿)   # Continue from above.
    ½𝒽⅀ (𝑃n↥𝛿 + 𝑝*𝑝ₘ√n↥√ʼm↧𝛿↑↓ + 𝑝*𝑝ₘ√ŉ↧√m↥𝛿↓↑ + 𝑃ŉ↧𝛿)
    ½𝒽⅀ (𝑃(n+1)𝛿 + 𝑝*𝑝ₘ√[n+1]√m𝛿↑↓ + 𝑝*𝑝ₘ√n√[m+1]𝛿↓↑ + 𝑃n𝛿)
    ½𝒽⅀ (𝑃(2n+1)𝛿 + 𝑝*𝑝ₘ√[n+1]√m𝛿↑↓ + 𝑝*𝑝ₘ√n√[m+1]𝛿↓↑)
    ½𝒽⅀{𝑃(2n+1)𝛿} + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    ½𝒽∑{𝑃(2n+1)} + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    ½𝒽∑{2𝑃n+𝑃} + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    ½𝒽∑{2𝑃n}+½𝒽∑{𝑃} + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    ½𝒽∑{2𝑃n}+½𝒽 + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    𝒽∑{𝑃n}+½𝒽 + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    𝒽ñ+½𝒽 + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    𝒽(ñ+½) + ½𝒽⅀{𝑝*𝑝ₘ√[n+1]√m𝛿↑↓} + ½𝒽⅀{𝑝*𝑝ₘ√n√[m+1]𝛿↓↑}
    𝒽(ñ+½) + ½𝒽⅀{𝑝↓*𝑝ₘ↑√[n]√[m+1]𝛿} + ½𝒽⅀{𝑝↑*𝑝ₘ↓√[n+1]√m𝛿}
    𝒽(ñ+½) + ½𝒽∑{𝑝↓*𝑝↑√[n]√[n+1]} + ½𝒽∑{𝑝↑*𝑝↓√[n+1]√n}
    𝒽(ñ+½) + ½𝒽∑{𝑝↓*𝑝↑√[n(n+1)]} + ½𝒽∑{𝑝↑*𝑝↓√[n(n+1)]}
    𝒽(ñ+½) + ½𝒽∑{𝑝↓*𝑝↑√[n(n+1)] + 𝑝↑*𝑝↓√[n(n+1)]}
    𝒽(ñ+½) + ½𝒽∑{√[n(n+1)](𝑝↓*𝑝↑ + 𝑝↑*𝑝↓)}
    𝒽(ñ+½) + ½𝒽∑{√[n(n+1)](𝑝ₙ₋₁*𝑝ₙ₊₁ + 𝑝ₙ₊₁*𝑝ₙ₋₁)}
    𝒽((ñ+½) + ½∑{√[n(n+1)](𝑝ₙ₋₁*𝑝ₙ₊₁ + 𝑝ₙ₊₁*𝑝ₙ₋₁)})

    ⧼𝐱²⧽ = ℏ/(μω) ((ñ + ½) + ½∑ {√[n(n+1)](𝑝ₙ₋₁*𝑝ₙ₊₁ + 𝑝ₙ₊₁*𝑝ₙ₋₁)})

###<a name="9QN"></a> ⧼𝐱²⧽-⧼𝐱⧽²

    ⧼𝐱²⧽-⧼𝐱⧽²
    𝒽((ñ + ½)+½∑{√[n(n+1)](𝒫↓↑+𝒫↑↓)}) - ½𝒽∑²{√[n+1]𝒫↑+√n𝒫↓}
    ñ𝒽 + ½𝒽 + ½𝒽∑{√[n(n+1)](𝒫↓↑+𝒫↑↓)} - ½𝒽∑²{√[n+1]𝒫↑+√n𝒫↓}
    𝒽(ñ + ½ + ½∑{√[n(n+1)](𝒫↓↑+𝒫↑↓)} - ½∑²{√[n+1]𝒫↑+√n𝒫↓})

> Just proceed?  :-??

###<a name="I9g"></a> ⧼𝐱⧽ₜ

    ⧼𝐱⧽ₜ
    ⧼x⧽ₜ                      # 𝐱 is just x.
    ⧼Ψₒₜ|ₙ⧽⧼ₙ|x|ₘ⧽⧼ₘ|Ψₒₜ⧽     # Expand out expression.
    ⨋ₓ (𝑝ₙ⌽ᵗₙΨₙ)*x(𝑝ₘ⌽ᵗₘΨₘ)   # Switched from ⧼⧽ to ⨋ₓ notation.
    ⨋ₓ (𝑝⌽Ψ)*x(𝑝ₘ⌽ₘΨₘ)        # Implicit ᵗ and ₙ, explicit ₘ.
    √𝒽⨋ (𝑝⌽Ψ)*ξ(𝑝ₘ⌽ₘΨₘ)       # Change of variable x to ξ.

The [𝒽](SCRATCH.md#hIf) is there because x=√𝒽ξ, a shorthand to ℏ/(μω).
It's just a constant.

    √𝒽⨋ (𝑝⌽Ψ)*ξ(𝑝ₘ⌽ₘΨₘ)                    # Continue from above.
    √𝒽⨋ (𝑝⌽ξΨ)*(𝑝ₘ⌽ₘΨₘ)                    # Rearrange, want ξΨ.
    √𝒽⨋ (𝑝⌽(√n↥Ψ↑+√ŉ↧Ψ↓))*(𝑝ₘ⌽ₘΨₘ)         # Substitue for ξΨ.
    √𝒽⨋ (𝑝⌽√n↥Ψ↑+𝑝⌽√ŉ↧Ψ↓)*(𝑝ₘ⌽ₘΨₘ)         # Distribute 𝑝⌽.
    √𝒽⨋ (𝑝φ↧⌽↑√n↥Ψ↑+𝑝φ↥⌽↓√ŉ↧Ψ↓)*(𝑝ₘ⌽ₘΨₘ)   # Match ⌽ quantum numbers.

Now here, I have to remind myself that I don't know 𝑝 yet.

    √𝒽⨋ (𝑝φ↧⌽↑√n↥Ψ↑+𝑝φ↥⌽↓√ŉ↧Ψ↓)*(𝑝ₘ⌽ₘΨₘ) # Continue from above.
    √𝒽⨋ ((𝑝φ↧⌽↑√n↥Ψ↑)*(𝑝ₘ⌽ₘΨₘ) + (𝑝φ↥⌽↓√ŉ↧Ψ↓)*(𝑝ₘ⌽ₘΨₘ)) # Distribute 𝑝ₘ⌽ₘΨₘ.
    √𝒽(⨋{(𝑝φ↧⌽↑√n↥Ψ↑)*(𝑝ₘ⌽ₘΨₘ)} + ⨋{(𝑝φ↥⌽↓√ŉ↧Ψ↓)*(𝑝ₘ⌽ₘΨₘ)}) # Separate sums.
    √𝒽(⨋{(𝑝φ↧√n↥)*(𝑝ₘ)𝛿↑} + ⨋{(𝑝φ↥√ŉ↧)*(𝑝ₘ)𝛿↓})
    √𝒽(⨋{(𝑝φ↧√n↥)*(𝑝↓)𝛿} + ⨋{(𝑝φ↥√ŉ↧)*(𝑝↑)𝛿})
    √𝒽(⨋{(𝑝φ↧√n↥)*(𝑝↓)𝛿} + ⨋{(𝑝φ↥√ŉ↧)*(𝑝↑)𝛿})
    √𝒽(⨋{φ↧*√n↥𝒫↓𝛿} + ⨋{φ↥*√ŉ↧𝒫↑𝛿})
    √𝒽(⨋{φ↧*√[n+1]𝒫↓𝛿} + ⨋{φ↥*√n𝒫↑𝛿})
    √𝒽(⨋{φ↥√[n]𝒫 𝛿} + ⨋{φ↧√[n+1]𝒫 𝛿})
    √𝒽(Σ{φ↥√[n]𝒫 } + Σ{φ↧√[n+1]𝒫 })
    √𝒽(Σ{φ↥√[n]𝑝*𝑝} + Σ{φ↧√[n+1]𝑝*𝑝})
    √𝒽Σ{φ↥√[n]𝑝*𝑝 + φ↧√[n+1]𝑝*𝑝}   # Joined sums.
    √𝒽Σ{𝑝*(φ↥√[n]𝑝+φ↧√[n+1]𝑝)}
    √𝒽Σ{𝑝*𝑝(φ↥√[n]+φ↧√[n+1])}
    √𝒽Σ{𝑃(φ↥√[n]+φ↧√[n+1])}
    √𝒽Σ{𝑃(c-s)√[n]+(c+s)√[n+1]}

At time 0, s=Sine is 0:

    √𝒽(Σ{𝑃(c√[n]+c√[n+1])})
    √𝒽c(Σ{𝑃(√[n]+√[n+1])}) # :-??

This is close to:

    √[2ñ𝒽]:Cosine[ωt]
    √[2ñℏ/(μω)]:Cosine[ωt]
    √[2Eₒ/(μω²)]:Cosine[ωt]
    √[2Eₒ/κ]:Cosine[ωt]

And that looks like equation 2.7 on the thesis.
So I'm doing something right, but I'm not sure this section is completely correct.

##<a name="eVh"></a> ⧼𝐩⧽

    ⧼𝐩⧽
    ⧼Ψₒ|ₙ⧽⧼ₙ|𝐩|ₘ⧽⧼ₘ|Ψₒ⧽
    ⨋ₓ (𝑝ₙΨₙ)* 𝐩 𝑝ₘΨₘ
    ⨋ₓ (𝑝Ψ)* 𝐩 𝑝ₘΨₘ                   # Implicit n, explicit m.
    ⨋ₓ (𝑝Ψ)*(-𝑖ℏ𝒟ₓ) 𝑝ₘΨₘ              # Wut 𝐩 is.
    ⨋ (𝑝Ψ)*(-𝑖ℏ𝛽𝒟) 𝑝ₘΨₘ               # Change of variable from x to ξ.
    ℏ𝛽⨋ (𝑝Ψ)*(-𝑖𝑝ₘ𝒟 Ψₘ)               # Rearrange.
    ℏ𝛽⨋ (𝑝Ψ)*(-𝑖𝑝ₘ√½(√ʼm↧Ψₘ↓-√m↥Ψₘ↑))
    ℏ𝛽⨋ (-𝑖𝑝*𝑝ₘ√½(√ʼm↧ΨΨₘ↓-√m↥ΨΨₘ↑))
    ℏ𝛽⅀ (-𝑖𝑝*𝑝ₘ√½(√ʼm↧𝛿↓-√m↥𝛿↑))
    ℏ𝛽⅀ (-𝑖𝒫 √½(√ʼm↧𝛿↓-√m↥𝛿↑))
    ℏ𝛽⅀ (-𝑖√½(√ʼm↧𝒫 𝛿↓-√m↥𝒫 𝛿↑))
    ℏ𝛽⅀ (-𝑖√½(√ʼ(m+1)↧𝒫↑𝛿-√(m-1)↥𝒫↓𝛿))
    ℏ𝛽∑ (-𝑖√½(√ʼ(n+1)↧𝒫↑-√(n-1)↥𝒫↓))       # :-??
    ℏ𝛽∑ (-𝑖√½(√ʼ(n+1)↧𝑝*𝑝↑-√(n-1)↥𝑝*𝑝↓))
    ℏ𝛽√½∑ (-𝑖𝑝*(√ʼ(n+1)↧𝑝↑-√(n-1)↥𝑝↓))
    ℏ𝛽√½∑ (-𝑖𝑝*(√[n+1]𝑝↑-√n𝑝↓))
    ℏ𝛽√½∑ (-𝑖𝑝*(√[n+1]𝑝ₙ₊₁-√n𝑝ₙ₋₁))

    ⧼𝐩⧽ = √[½ℏμω] ∑{-𝑖𝑝*(√[n+1]𝑝ₙ₊₁ - √[n]𝑝ₙ₋₁)}

    ℏ𝛽∑ (-𝑖√½(√ʼ(n+1)↧𝒫↑-√(n-1)↥𝒫↓))       # :-??
    ℏ𝛽∑{-𝑖√½(√ʼ(n+1)↧𝒫↑-√(n-1)↥𝒫↓)}
    -𝑖ℏ𝛽√½∑{√ʼ(n+1)↧𝒫↑-√(n-1)↥𝒫↓}
    -𝑖ℏ𝛽√½(∑{√ʼ(n+1)↧𝒫↑} - ∑{√(n-1)↥𝒫↓})   # Separate sums.
    -𝑖ℏ𝛽√½(∑{√[n+1]𝒫↑} - ∑{√n𝒫↓})
    -𝑖ℏ𝛽√½(∑{√[n+1]𝑝*𝑝↑} - ∑{√n𝑝*𝑝↓})
    -𝑖ℏ𝛽√½(∑{√n𝑝↓*𝑝} - ∑{√n𝑝*𝑝↓})

    -𝑖ℏ𝛽√½(∑{√n(𝑝*𝑝↓)*} - ∑{√n𝑝*𝑝↓})
    -𝑖ℏ𝛽√½(∑{√n𝒫↓*} - ∑{√n𝒫↓})
    ℏ𝛽√½(∑{√n𝑖𝒫↓} - ∑{√n𝑖𝒫↓*})

> Well... of course!
> OMG, I get it.
> LOL!
> If the state like c-is, then
> x is going to be like c, and
> p is goint to be like s:

    1(c-𝑖s) + 1(c-𝑖s)* = 2c   # This is x
    𝑖(c-𝑖s) - 𝑖(c-𝑖s)* = 2s   # This is p

> I'll clean this up later.

###<a name="8BU"></a> ⧼𝐩⧽²

    ⧼𝐩⧽²
    (√[½ℏμω] ∑{-𝑖𝑝*(√[n+1]𝑝ₙ₊₁ - √[n]𝑝ₙ₋₁)})²
    (ℏ𝛽√½∑{-𝑖(√[n+1]𝒫↑-√[n]𝒫↓)})²
    ½ℏ²𝛽²(∑{-𝑖(√[n+1]𝒫↑-√[n]𝒫↓)})²
    -½ℏ²𝛽²(∑{√[n+1]𝒫↑-√[n]𝒫↓})²   # I should be able to do that!
    -½ℏ²μω/ℏ(∑{√[n+1]𝒫↑-√[n]𝒫↓})²
    -½ℏμω(∑{√[n+1]𝒫↑-√[n]𝒫↓})²

    ⧼𝐩⧽²
    (ℏ𝛽√½(∑{√n𝑖𝒫↓} - ∑{√n𝑖𝒫↓*}))²
    (ℏ𝛽√½)²(∑{√n𝑖𝒫↓} - ∑{√n𝑖𝒫↓*})²
    ½ℏμω(∑{√n𝑖𝒫↓} - ∑{√n𝑖𝒫↓*})²
    ½ℏμω(∑²{√n𝑖𝒫↓} - 2∑{√n𝑖𝒫↓}∑{√n𝑖𝒫↓*} + ∑²{√n𝑖𝒫↓*})
    ½ℏμω(-∑²{√n𝒫↓} + 2∑{√n𝒫↓}∑{√n𝒫↓*} - ∑²{√n𝒫↓*})
    ½ℏμω(-∑²{√n𝒫↓} + 2⅀{√n√m𝒫↓*𝒫↓} - ∑²{√n𝒫↓*})
    ½ℏμω(-∑²{√n𝒫↓} + 2⅀{√n√[m+1]𝒫*𝒫} - ∑²{√n𝒫↓*})

##<a name="TRj"></a> ⧼𝐩²⧽

    ⧼𝐩²⧽
    ⧼Ψₒ|ₙ⧽⧼ₙ|𝐩²|ₘ⧽⧼ₘ|Ψₒ⧽
    ⨋ₓ (𝑝ₙΨₙ)* 𝐩² 𝑝ₘΨₘ
    ⨋ₓ (𝑝Ψ)* 𝐩² 𝑝ₘΨₘ
    ⨋ₓ (𝑝Ψ)* 𝐩𝐩 𝑝ₘΨₘ
    ⨋ₓ (𝐩*Ψ)* 𝑝*𝑝ₘ 𝐩Ψₘ
    ⨋ₓ 𝒫 (𝐩*Ψ)*(𝐩Ψₘ)
    ⨋ₓ 𝒫 (𝑖ℏ𝒟ₓΨ)*(-𝑖ℏ𝒟ₓΨₘ)
    ℏ²⨋ₓ 𝒫 (𝒟ₓΨ)*(𝒟ₓΨₘ)
    ℏ²⨋ 𝒫 (𝛽𝒟 Ψ)*(𝛽𝒟 Ψₘ)
    ℏ²𝛽²⨋ 𝒫 (𝒟 Ψ)*(𝒟 Ψₘ)
    ℏ²/𝒽 ⨋ 𝒫 (𝒟 Ψ)*(𝒟 Ψₘ)
    ℏμω ⨋ 𝒫 (𝒟 Ψ)*(𝒟 Ψₘ)
    ℏμω ⨋ 𝒫 (√½(√ŉ↧Ψ↓-√n↥Ψ↑))*(√½(√ʼm↧Ψₘ↓-√m↥Ψₘ↑))
    ½ℏμω ⨋ 𝒫 (√ŉ↧Ψ↓-√n↥Ψ↑)*(√ʼm↧Ψₘ↓-√m↥Ψₘ↑)
    ½ℏμω ⨋ 𝒫 (√ŉ↧Ψ↓√ʼm↧Ψₘ↓-√ŉ↧Ψ↓√m↥Ψₘ↑-√n↥Ψ↑√ʼm↧Ψₘ↓+√n↥Ψ↑√m↥Ψₘ↑)
    ½ℏμω ⅀ 𝒫 (√ŉ↧√ʼm↧𝛿↓↓-√ŉ↧√m↥𝛿↓↑-√n↥√ʼm↧𝛿↑↓+√n↥√m↥𝛿↑↑)
    ½ℏμω ⅀{√ŉ↧√ʼm↧𝒫 𝛿↓↓-√ŉ↧√m↥𝒫 𝛿↓↑-√n↥√ʼm↧𝒫 𝛿↑↓+√n↥√m↥𝒫 𝛿↑↑}
    ½ℏμω ⅀{√n√m𝒫 𝛿↓↓-√n√[m+1]𝒫 𝛿↓↑-√[n+1]√m𝒫 𝛿↑↓+√[n+1]√[m+1]𝒫 𝛿↑↑}
    ½ℏμω ⅀{√[n+1]√[m+1]𝒫↑↑𝛿-√[n+1]√m𝒫↑↓𝛿-√n√[m+1]𝒫↓↑𝛿+√n√m𝒫↓↓𝛿}
    ½ℏμω ∑{√[n+1]√[n+1]𝒫↑↑-√[n+1]√n𝒫↑↓-√n√[n+1]𝒫↓↑+√n√n𝒫↓↓}
    ½ℏμω ∑{(n+1)𝒫↑↑-√[n(n+1)]𝒫↑↓-√[n(n+1)]𝒫↓↑+n𝒫↓↓}
    ½ℏμω ∑{n𝒫 -√[n(n+1)]𝒫↑↓-√[n(n+1)]𝒫↓↑+(n+1)𝒫 }
    ½ℏμω ∑{2n𝒫 -√[n(n+1)]𝒫↑↓-√[n(n+1)]𝒫↓↑+𝒫 }
    ½ℏμω ∑{2n𝒫 + 𝒫 -√[n(n+1)]𝒫↑↓-√[n(n+1)]𝒫↓↑}
    ½ℏμω((2ñ+1) - ∑{√[n(n+1)]𝒫↑↓+√[n(n+1)]𝒫↓↑})
    ½ℏμω((2ñ+1) - ∑{√[n(n+1)](𝒫↑↓+𝒫↓↑)})
    ½ℏμω((2ñ+1) - ∑{√[n(n+1)](𝑝↑*𝑝ₘ↓+𝑝↓*𝑝ₘ↑)})
    ½ℏμω((2ñ+1) - ∑{√[n(n+1)](𝑝ₙ₊₁*𝑝ₘ₋₁+𝑝ₙ₋₁*𝑝ₘ₊₁)})

    ⧼𝐩²⧽ = ½ℏμω((2ñ+1) - ∑{√[n(n+1)](𝑝ₙ₊₁*𝑝ₘ₋₁+𝑝ₙ₋₁*𝑝ₘ₊₁)})

###<a name="7HF"></a> ⧼𝐩²⧽-⧼𝐩⧽²

    ⧼𝐩²⧽-⧼𝐩⧽²
    ½ℏμω((2ñ+1)-∑{√[n(n+1)](𝒫↑↓+𝒫↓↑)}) - -½ℏμω(∑{√[n+1]𝒫↑-√[n]𝒫↓})²
    ½ℏμω((2ñ+1)-∑{√[n(n+1)](𝒫↑↓+𝒫↓↑)}) + ½ℏμω(∑{√[n+1]𝒫↑-√[n]𝒫↓})²

###<a name="zcf"></a> (⧼𝐱²⧽-⧼𝐱⧽²)(⧼𝐩²⧽-⧼𝐩⧽²)

    ℏ/(μω)((ñ+½) + ½∑{√[n(n+1)](𝒫↓↑+𝒫↑↓)} - ½∑²{√[n+1]𝒫↑+√n𝒫↓})   # ⧼𝐱²⧽-⧼𝐱⧽² = Δ²𝐱
    ℏ  μω ((ñ+½) - ½∑{√[n(n+1)](𝒫↑↓+𝒫↓↑)} + ½∑²{√[n+1]𝒫↑-√n𝒫↓})   # ⧼𝐩²⧽-⧼𝐩⧽² = Δ²𝐩

> It's almost perfectly symetrical.
> I probably messed up the algebra for ⧼𝐩⧽² somewhere.

##<a name="2Nz"></a> Resources
On top of the references given in the appendix,
I'd like to add (or reiterate) the following resources:

* Liboff's book, [Introductory Quantum Mechanics](https://books.google.com/books?id=FbIPAQAAMAAJ&dq=editions:0s8yO_VH82AC&hl=en&sa=X&ei=v5L9VNCcBpLkoATB1IGAAQ&ved=0CDsQ6AEwBg).
* njwildberger's [MathFoundations](https://www.youtube.com/playlist?list=PL5A714C94D40392AB)
* Stanford's Susskind's [Advanced Quantum Mechanics](https://www.youtube.com/playlist?list=PLpGHT1n4-mAsmMxmSX0LCaXIXT2PmU85m)
* jodiecongirl's [A Lagrange Multiplier Example](https://youtu.be/H4HN4ZrVm0w)
* mathdude2012's [Uncertainty Principle with Time and Energy](https://www.youtube.com/watch?v=Eb3V8GrR7jk)
* professofleonard57's [Series, Geometric Series, Harmonic Series, and Divergence Test](http://youtu.be/DGcWMdW-72M)
* MindYourDecisions' [What is the factorial of 1/2? The surprising answer: (1/2)!=(√π)/2](http://youtu.be/QhDDpSju3uY)
* yourteachermathhelp's [Geometry Proofs - Algebra Proofs - MathHelp.com](http://youtu.be/WXzpisUh0AU)
* sidlmorris' [Topology Without Tears - Video 4a - Writting Proofs in Mathematics](http://youtu.be/T1snRQEQuEk)
* DMAshura's [Introduction to Higher Mathematics](https://www.youtube.com/user/DMAshura/playlists)

So the way it works is that any mistakes herein are all my fault.
If I say anything good, it's because of these other people:
