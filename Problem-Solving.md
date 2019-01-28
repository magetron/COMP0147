# Problem solving class - 1

## 4.

A = (n Ai)^c

B = (U Ai^c)

A is a subset of B
x belong A -> x not belong (n Ai) -> not (forall i) x belong Ai -> exsist i (x not belong Ai) -> exsist i ( x belong Ai^c) 
-> x belong (U Ai^c)

B is a subset of A
y belong B -> exsist i (y belong Ai^C) -> exsist i (y not belong Ai) -> not (forall i) y belong Ai -> y not belong (n Ai) -> y belong (n Ai)^c

## 4.(Extra)

A = (U Ai)^c
B = (n Ai^c)

A is a subset of B
x belong A -> x not belong (U Ai) -> (forall i) x not belong Ai -> (forall i) x belong Ai^c -> x belong (n Ai ^ c)

B is a subset of A
y belong B -> (forall i) y belong Ai^c -> (forall i) y not belong Ai -> y not belong (U Ai) -> y belong (U Ai)^c

## 6.

Bn = ( -1/n, 1]

WTS n Bn = [0, 1]

A = n Bn 
B = [0, 1]

x belong A -> x belongs n Bn -> (for all n) x belongs Bn 

-> x belong (-1/n, 1] -> x <= 1

-> WTS x < 0 is impossible -> x >= 0

if x < 0 then exsist n such that x < - 1/n
such that x >= 0

x >= 0 x <= 1 -> x belong [0, 1]


y belong B -> 0 <= y <= 1 -> (for all n) y belong Bn -> y belong n bn


## 3.

D = A x (B U C) = (A x B) U (A x C) = H

(x, y) belongs D => (x, y) belongs H

x belongs A, y belongs B U C  
-> y belongs B
   x belongs A
   (x, y) belongs A x B
   (x, y) belongs H

-> y belongs C
   (x, y) belongs A x C
   (x, y) belongs H

(x, y) belongs H => (x, y) belongs D
-> (x, y) belongs A x B 
   x belongs A, y belongs B, y belongs B U C
   (x, y) belongs D

-> (x, y) belongs A x C
   x belongs A, y belongs c, y belongs B U C
   (x, y) belongs D


# Problem Solving Class - 3

> Reminder for Group
> 1. Closiness (Closure) Stays in the group after operation
> 2. Associativity (a * b) * c = a * (b * c)
> 3. Neutral element
> 4. Inverse element for every element in the group

## 1.

### a)

Inverse element not found for 2 ... (e.g 2 * (1 / 2) = 1)

1 / 2 is not in the group

### b)

Neutral element requires to be communitive.

Therefore, x - 0 = x
However, 0 - x != x. 
Thus, there is no neutral element.

Associativity not satisfied for all elements

(x - y) - z != x - (y - z)

### c)

ε = -1

x . y = -1

x + y + 1 = -1 

y = - x - 2

## 3.

### c)
x^3 in Q, y^3 in Q

(x * y)^3 = x^3 * y^3 in Q

C is a group, it is a subgroup of G(R, *)
