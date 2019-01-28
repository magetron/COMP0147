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

### Example

{1, 2 .. n} -> {1, 2 .. n}
bijection

1 -> σ(1)
2 -> σ(2)
...
Array is a bijection, permutation. 

Foreach position, biject an object / number.

All sorting procedure is based on swap.

bubble sort -> O(n ^ 2) exchange

Qsort -> O(n ^ 2) at most / O(n lg n) most of the time.

Permutation has practical implication in Computer Science.

### Example 2

a1 < a2 < a3

| 1  | 2  | 3  |
|----|----|----|
| a3 | a1 | a2 |

--> sorting

| 1  | 2  | 3  |
|----|----|----|
| a1 | a2 | a3 |

σ
1 -> a3
2 -> a1
3 -> a2 

σ^2
a1 -> aa3
a2 -> aa1
a3 -> aa2

σ^3
aa1 -> aaa3
aa2 -> aaa1
aa3 -> aaa2

Sorted !
1 -> aaa1
2 -> aaa2
3 -> aaa3

The number of permutation to get a sorted result might be awful.

σ
1 -> a1
2 -> a3
3 -> a2

σ^2
a1 -> aa1
a2 -> aa3
a3 -> aa2

1 -> aa1
2 -> aa2
3 -> aa3 

Sorted!

### Definition

σ^k = e where e is the identity permutation

The order of permutation σ is the smallest possible integer k.

All {1, 2, 3} permutation can be sorted in k = 2 / k = 3.

### Sgn

1  2  3
a3 a1 a2

a3 < a2
a3 < a1  -> 2 disorders

sgn(σ) = (-1)^2 = 1

1  2  3
a2 a1 a3

a2 < a1 -> 1 disorder

sgn(σ) = (-1)^1 = 1

sgn respects our composition

For any two permutation σ1 σ2

sgn(σ1σ2) = sgn(σ1) • sgn(σ2)

| σ    | EVEN | ODD  |
|------|------|------|
| EVEN | EVEN | ODD  |
| ODD  | ODD  | EVEN |


## Binary Relations
P(x, y)

"x < y"
"x <= y"
"y = x^ (2n)"
"x is a child of y"
"x is a pointer to cell that contains y"
"x and y are students of one and the same school"

### Equivalence Relations E(x, y)

"Reflexivity" (forall x) E(x, x)
"Symmetry"    (forall x, y) E(x, y) -> E(y, x)
"Transitivity" (for all x, y, z) E(x, y) and E(y, z) -> E(x, z)

E(x, y) = " x = y "
E(x, y) = " x^2 = y^2 "

E2(x, y) = " x - y is even" modulo 2
E2(x, x) = True
E2(x, y) -> E2(y, x) True
Since x - y is even -> x - y = 2n / y - x = -2n is even
E2(x, y) and E2(y, z) -> E2(x, z)
x - y = 2k y - z = 2m
x - z = (x - y) + (y - z) = 2k + 2m = 2(k + m) is even

E2 is also an equivalence relation.

[k]2 = {y | E2(k, y) }

[0]2 = {0, 2, -2, 4, -4, ... 2n, -2n} <- even

[1]2 = {1, 3, -1, -3, ... 2n + 1 ...} <- odd

Z / E2 = {EVEN, ODD}

### Congruence - Respects + and x

Equivalence relation E2 divide Z in two partitions.

All partitions can be expressed by Equivalence relations.

[1] + [1] = [2] 
sum of any two number in [1] gives us all even numbers [2]

[1 + 1] = [2] even

### Example

E3(x, y) = "x - y is divisible by 3"

[0] [1] [2] ([3] = [0])

[a] + [b] = [a + b]

[2] + [2] = [4] = [1]

Em(x, y) = "x = y (mod m)"

> Note by : Properties of + and x
> Associativity 
> (a + b) + c = a + (b + c)
> (a * b) * c = a * (b * c)
> Communicative a + b = b + a
> a * b = b * a
> Specific Number (Neutral Element) 
> a + 0 = a
> a * 1 = a
> Inverse Action / Operation
> a + x = a - (-x)
> a * x = a / (1 / x)

### Group

Group (G, o, e, a ^ {-1})

G - set
o - binary operation
e - netural element
a ^ {-1} - inverse operation

### Example

mod 7

2 4 (8 = 1 (mod 7))

x 3 {3, 2, 6, 4, 5, 1} <- finite group <- if I compute multiple times, i will always get 1 (we can simplify big number)

## Equivalence : x = y (mod m)

### Definition 

Em(x, y) = "(x - y) is divisible by m"

k (mod m) = [k]m = {y | (y - k) is divisible by m}

[10]3 = {10, 7, 13, 1 ...} all those numbers that have the same mod 3 as 10.
		    r <- this is the remainder, which is the most typical representative of the class

### The set of "remainders"

Gm = {0, 1, 2} 
[0]3 = [3]3

#### Introducing + to Gm

| + (mod 3) | 0 | 1 | 2 |
|-----------|---|---|---|
| 0         | 0 | 1 | 2 |
| 1         | 1 | 2 | 0 |
| 2         | 2 | 0 | 1 |

[a]3 + [b]3 = [a + b]3

[2]3 + [1]3 = [3]3 = [0]3 <- better representative

[2]3 + [2]3 = [4]3 = [1]3 <- same reason

#### Introducing * to Gm

| * (mod 3) | 0 | 1 | 2 |
|-----------|---|---|---|
| 0         | 0 | 0 | 0 |
| 1         | 0 | 1 | 2 |
| 2         | 0 | 2 | 1 |

## Group

A nonempty set G together with a binary operation 

`* : G x G -> G`

`(G *)` is a group iff

* a) Closure : forall x, y ((x belongs G) and (y belongs G) -> (x * y belongs G))
* b) Associativity : for any x, y, z from G. (x * y) * z = x * (y * z)
* c) Neutral: For some (unique ) ε belongs G -> forall x belongs G (x * ε = ε * x = x)
* d) Invertibility: forall x belong G (exsist y belong G (x * y = y * x = ε)) Such unique y is denoted as y = x ^ -1

For any group `(G *)` :
* (a) The neutral element ε is unqiue.
* (b) The inverse element x ^ -1 is unique
* (c) For any a, b belongs G, the equation a * x = b has a unique solution: x = a ^ -1 * b

	Proof : 	a * x = b 
		<=>	a ^ -1  * a * x = a ^ -1 * b
		<=>	ε * x = a ^ -1 * b
		<=>	x = a ^ -1 * b

> Informally, x = 1 / a * b = b / a

	Proof :	There is a unique inverse element
		Let x belongs G, y1, y2, belongs G
			x * y1 = ε
			x * y2 = ε
			y1 * (x * y1) = ε * y1 = y1
			y1 * (x * y2) = y1 * ε = y1
			(y1 * x) * y2 = y1
			ε * y2 = y1
			y1 = y2

(a) x,y belongs R+ => x * y belongs R+
(b) x * (y * z) = (x * y) * z
(c) ε belongs R+ x * 1 = 1 * x = x
(d) x belongs R+, y belongs R+, x * y = 1

For R, (d) doesn't satisfy. since there is no inverse of 0.

### An Example : Permutation

Sn is all permutation of 
1 2 3 ... n

(a) σ1σ2 = σ3 Yes.
(b) σ1(σ2σ3) = (σ1σ2)σ3 Yes.
(c) ε = (1, 2, 3 ... n) -> (1, 2, 3 ... n) Yes.
(d) σ = (1, 2, 3) -> (3, 1, 2) <-> σ ^ -1 = (1, 2, 3) -> (2, 3, 1) Yes. Any bijection has an inverse bijection.

Permutation form a group.

#### Example

ε = 
(1 2 3)
(1 2 3)

σ1 =
(1 2 3)
(2 3 1)

σ2 = σ1 ^ 2
	(1 2 3)
-> 	(2 3 1)
->	(3 1 2)

σ2σ1 =
	(1 2 3)
->	(3 1 2)
->	(1 2 3)

σ2 ^ -1 =
	(1 2 3)
->	(2 3 1)
= σ1

σ2σ1 = σ1 ^ 2 σ1 = ε
σ1 ^ 3 = ε
σ2σ2 = σ1 ^ 4 = σ1 
	(1 2 3)
->	(3 1 2)
->	(2 3 1)

(a) a, b belong G -> ab belongs G
(b) yes.
(c) yes ε
(d) σ ^ -1 should belong to G

Multiplication Table:
| o  | ε  | σ1 | σ2 |
|----|----|----|----|
| ε  | ε  | σ1 | σ2 |
| σ1 | σ1 | σ2 | ε  |
| σ2 | σ2 | ε  | σ1 |

ε, σ1, σ2  cyclic group.

We have an identical Multiplication Table above with + (mod 3).

#### Example

Sn <- all possible permutations

An = { σ belongs Sn | σ is even)

(a) sgn(σ1σ2) = sgn(σ1)sgn(σ2) is even
(b) yes
(c) ε
(d) sgn(σ σ ^ -1) = ε

**Homework : Make a table for A3**

### Groups : An "additive" Style

`(G, +)`

c) Neutral Element : 0
d) Inverse denoted as y = -x

a) neutral element 0 is unique
b) inverse element -x is unique
c) for any a and b from G, the equation a + x = b has a unqiue solution x = b + (-a) = b - a (informally)

|   | (Z, +)        | (N, +)                |
|---|---------------|-----------------------|
| a | Yes           | Yes                   |
| b | Yes           | Yes                   |
| c | 0             | 0                     |
| d | x + y = 0 Yes | No. -x doesn't exsist |

(Z, +) is a group.


### Subgropus
G Sn

An = { σ belongs Sn | σ is even }
Bn = { σ belongs Sn | σ is odd }

An U Bn = Sn

H is a subset of G.

`(H, *)` H inherent operations from G.

How to check `(H, *)` is a group?

(a) x, y belongs H -> x * y belongs H *(SHOULD be checked)*
(b) no need to check (provided by G)
(c) check that ε belongs H. *(SHOULD be checked)*
(d) inverse forall x belongs H (exsist y belongs H (x * y = y * x = ε)) *(SHOULD be checked)*

go back to An above.

An is a subset and a subgroup.
(a) yes
(b) yes
(c) yes
(d) yes sgn(σ^-1 σ) = 0sgn(ε) = +1
	sgn(σ^-1)sgn(σ) = +1

Bn is a subset not a group.
(c) ε doesnot carry on.

If H is a subgroup of G (which is finite)

|H| divides |G|.

#### Example

G = ({1, 2, 3, 4}, (* | mod 5)}

| G | 1 | 2 | 3 | 4 |
|---|---|---|---|---|
| 1 | 1 | 2 | 3 | 4 |
| 2 | 2 | 4 | 1 | 3 |
| 3 | 3 | 1 | 4 | 2 |
| 4 | 4 | 3 | 2 | 1 |

ε = 1

2y = 1  -> y = 3

2^(-1) = 3

3y = 1  -> y = 2

3^(-1) = 2

4y = 1  -> y = 4

4^(-1) = 4

The particular subgroup we are looking for is called cyclic subgroup.


#### Cyclic Group

a^-2, a^-1, 1, a a^2 ..

In our example, 1, 2, 4, 3(2^3), 1(2^4), 4(2^5) ...

Group c (cyclic group) i identical to the Group G.

Also, anthoer example start with 3.

3, 4, 2, 1, ...

There is no actual subgroup for this case.

#### Example

H = ({1, 5} * mod 6)

(2 - 1) * (3 - 1)

| H | 1 | 5 |
|---|---|---|
| 1 | 1 | 5 |
| 5 | 5 | 1 |

#### Example 

H = ({1, 2, 4, 8} * mod 15)

15 = 3 * 5

{1, 2, 4, 7, 8, 10, 11, 13, 14}

|G| = 8
