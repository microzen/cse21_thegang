# Assignment 5

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: November 18 2025

### Question 4
For each situation below, first give the recurrence for the runtime of the algorithm (no
explanation for this part.) Then use the Master Theorem, if possible, and give the values for a b and d and the O bound.

a) Suppose an algorithm solves a problem of size n by recursively calling 2 subproblems each of size $2n/5$. Then the non-recursive part of the algorithm takes $O(n^2)$ time.

Solution:

Recurrence:

$f(n) = 2f(\displaystyle\frac{2n}{5}) + O(n^2)$

Master Theorem:

a = 2, b = 5/2, d = 2

$ a < b^d$

$T(n) = O(n^2)$

b) Suppose an algorithm solves a problem of size n by recursively calling 2 subproblems each of size n/4. Then the non-recursive part of the algorithm takes $O(\sqrt{n})$ time.

Solution: 

Recurrence:

$f(n) = 2f(\displaystyle\frac{n}{4}) + O(\sqrt{n})$

Master Theorem:

a = 2, b = 4, d = 1/2

$ a = b^d$

$T(n) = O(n^{0.5}\log{n})$

c) Suppose an algorithm solves a problem of size n by recursively calling 2 subproblems each of size
n/4. Then the non-recursive part of the algorithm takes $O(n^{1.5})$ time.

Solution:

Recurrence:

$f(n) = 2f(\displaystyle\frac{n}{4}) +O(n^{1.5})$

Master Theorem:

a = 2, b = 4, d = 1.5

$ a < b^d$

$T(n) = O(n^{1.5})$
