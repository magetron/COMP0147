# COMP0147

## Preface

### Foundations

* a) Sets theoretic notation. Binary relations. Modular arithmetic. Functions. Injections, surjections, bijections and their inverses. Cardinality of sets.

* b) The symmetry group, disjoint cycle noatation; the sign of permutation. Abstract grups and Lagrange's Theorem.

* c) Euclid's alogirhm, solving linear congruences. Fermat's little theorem, the Eulertotient function, application to public key cryptography.

### Linear Algebra

### Counting

* a) Counting. Combinations, permutations, binomial theorem.


## Sets

### Muchess

muchness = set
"much of a muchness" = "set of sets"

### Sets, subsets

#### Notation

A = {a, b, c}, a belongs A

{x | x is a real s.t. x ^ 2 = x} {x : x ^ 2 = x}

The empty set ø

**NB: No structure, no order, no copies.**

{a, b, c} = {c, a, b} = {a, b, c, b}

a, b, c are pointers.

A belongs B - this is for all x (x belongs A) -> (x belongs B)
B belongs A - vice versa.

If A belongs B && B belongs A then A = B.

#### Operations

A U B = { x | (x belongs A) or (x belongs B) }

A n B = { x | (x belongs A) and (x belongs B) }

A \ B = { x | (x belongs A) and (x not belongs B) } (unique to A)

A ∆ B = (A U B) \ (A n B) -> A = {a1, a2, b1, b2} B = {a1, b1, b3} -> A ∆ B = {a2, b2, b3}

A x B = { (x, y) | (x belongs A) and (y belongs B) } -> sets of tuples

A ^ c (compliment) = U \ A = { x | (x belongs U) and (x not belongs to A) } -> U Universal Set.

Why U? To cope with `Russell's Paradox.``

**NB: Undecidable problems in CS`

## Set Algebra

### A n (B U C) = (A n B) U (A n C)  kinda similar to x * (y + z) = (x * y) + (x * z)

### A U (B n C) = (A U B) n (A U C) kinda similar to x + (y * z) = (x + y) * (x + z)
	|		|
	v 		v
	X		Y

* X belongs Y

x belongs X. 	
- x belongs A -> x belongs A U B, x belongs A U C.-> x belongs Y
- x belongs (B n C), -> x belongs B, x belongs C. -> x belongs A U C, x belongs A U B ->  x belongs (A U C) n (B U C) = Y


* Y belongs X
y belongs Y.
- y belongs (A U B), y belongs (A U C) -> y belongs A or y belongs B n C ->  y belongs X.


### A \ B = A n (B ^ c)

* x belongs A \ B -> x belongs A and x not belongs B.  -> x belongs A and x belongs B ^ c ->  x belongs A n (B ^ c)

* y belongs A n (B ^ c) -> y belongs A and y belongs B ^ c -> y belongs A and y not belongs B -> y belongs A \ B


### (A U B) ^ c = A^c n B^c De Morgan's Law

* x belongs (A U B) ^ c -> x not belongs A and x not belongs B -> x belongs to A^c or x belongs B^c -> x belongs A^c n B^c

* y belongs A^c n B^c -> y belongs A^c or y belongs B^c -> y not belongs A and y not belongs B -> y belongs (A U B) ^c

### (C n D) ^ c = C^c u D^c

(C n D)^cc = (C^c u D^c)c

C n D  = (C^c u D^c)^c

C^c = A, D^c = B

(A u B)^c = A^c n B^c = C n D

#### A = B iff A^c = B^c

#### A belongs B -> B^c belongs A^c Counter Position Law

similar to p -> q == not q -> not p

### Infinite Union

A1 A2 ... An i belongs Index

x belongs n (i = I) Ai iff for all i belongs I, x belongs Ai.

y belongs U (i = I) Ai iff exsist i belongs I, y belongs Ai

**(U (i = I) Ai )^c = n ((i = I) Ai^c)**

## Functions

f: X -> Y

Mapping X to Y. x1 -> f(x1), x2 -> f(x2)

X = domain(f) set of input
Y = range(f) = image(f) = { y | exsist x belongs X (y = f(x)) }

* Example : for f(x) = x^2, Range(f) = {r | r >= 0 }

Total function where domain(f) = X

Partial Function where domain(f) <= X

### Category

* range(f) = Y. -> Surjective / On to mapping.

f is onto iff for all y belongs Y, f(x) = y has at least one solution.

* if x1 != x2 -> f(x1) != f(x2)  for all x1, x2 in X. f is a Injection function

f is an injection function iff for all y belongs Y, f(x) = y has at most one solution.

* If both (on to mapping) and (injection) = f is a bijection function

f is bijection iff for all y belongs Y, f(x) = y has only one solution. (always have one and only one)

if exsists f that maps X -> Y, |X| = |Y|. f produces one-to-one correspondence.


### Function common sets

N = {0, 1 ...}

Z = { integer }

Q = { rational  -> p / q }

R = { real }

### Q -> N

p/q -> rational (p, q > 0)

f(p, q) = 2^p * (2q + 1)

binary representation of q 010100101.... with 1 at the bottom -> 2q + 1
binary representation of p 000101011 (00000) with 0s at the bootom -> 2^p

|Q| = |N| = Na since f is bijection. (a for alpha, Na means the number of elements in N)

countable and enummerable.

|(0, 1)| (Real) cannot be bijected with |N|

|X| = |Y|  -> |X| >= |Y|  and  |Y| >= |X|


### Example

f(x) = x ^ 2 not surjective (cannot produce -1 ...)

f(x) = x ^ 3 surjective

f(n) = 2n not surjective (cannot produce 1, 3 ...)

f(x) = x ^ 2 not injective (+ / -2 produces 4)

f(x) = x ^ 3 injective

f(n) = 2n injective

Both injection and surjection -> bijection

### Composition of Injections

h = f o g is misleading. 

we use h = f ; g

  (f)    (g)
X ---> Y ---> Z

x1 --> y1 --> z1
x2 --> y2 --> z2

since f & g are injection, since x1, x2 are different, z1, z2 are differnt


## Cardinality. How to compare sets: |X| <= |Y|

if there exsists an injective function f encoding X -> Y

f : X -> Y

### |Q+| <= |N|

We can encode non-negative rationals with the following injection f withc encode any (p / q) with a nautral number 2 ^ p * (2q + 1)

### |X| = |Y|

If we can produce a bijection function (1 to 1 correspondence) h : X -> Y then |X| = |Y|

### Cantor-Bernstein Theorem

(|X| <= |Y|) and (|Y| <= |X|) -> (|X| = |Y|)

Given an injective function f : X -> Y  and an injective function  g : Y -> X. Therefore, one can construct bijection h : X -> Y betwen X and Y.

### Important Conclusions

countable, enumberable sets : |Q| = |Z| = |N| = Na

the continious is not countable : |R| > Na

## Permutations Sn. How to coount permutations. |Sn| = n!

sgn(σ) = (-1) ^ k is defined by the number k of "disorders". -> number k of pairs (x, y) that x < y but σ(x) > σ(y)

sgn(σ) = - 1 odd

sgn(σ) = 1 even
