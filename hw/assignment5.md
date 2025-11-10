# Assignment 5

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: November 18 2025

### Question 3

Modular Exponentiation is needed for some cryptography applications. For example, the Diffie-Hellman protocol and the RSK algorithm use modular exponentiation.

A modular exponentiation algorithm takes 3 positive integers as inputs: $b > 1, x \geq 0, n > 1$ and it returns the value of $b^x \bmod n$.

In these applications, the integers used b, x, n are usually very large (sometimes with hundreds of digits.) and so they won't be able to fit into word size.

Consider the following algorithm:

```
FastModExp(b, x, n)
1. if x == 0:
2.     return 1
3. if x is even:
4.     F = FastModExp(b, x/2, n)
5.     F' = F²
6.     return F' % n
7. if x is odd:
8.     F = FastModExp(b, x-1, n)
9.     F' = F × b
10.    return F' % n
```

(8 points) Prove the correctness of this algorithm (hint: Fix the variables b and n and induct on the variable x.)

Proof by induction on $x$.
Fix arbitrary integers $b > 1$ and $n > 1$.

Base case:

When $x = 0$, the algorithm correctly returns $1$ since $b^0 \bmod n = 1$.

Inductive hypothesis:

Let $x \geq 1$.
Assume that the algorithm correctly returns $b^k \bmod n$ for all $k$ such that $0 \leq k < x$.

Inductive step:

We want to show $\text{FastModExp}(b, x, n) = b^x \bmod n$.

Case 1: $x$ is even

The algorithm calls $\text{FastModExp}(b, x/2, n)$, stores the result in $F$, then computes $F' = F^2$, and returns $F' \bmod n$.

By the inductive hypothesis (since $x/2 < x$),

$$
F = b^{x/2} \bmod n
$$

Therefore, the algorithm returns:

$$
\begin{aligned}
F' \bmod n &= (F^2) \bmod n \\
&= ((b^{x/2} \bmod n)^2) \bmod n \\
&= (b^{x/2})^2 \bmod n \quad \text{(by mod exponentiation property*)} \\
&= b^x \bmod n \quad
\end{aligned}
$$

Case 2: $x$ is odd

The algorithm calls $\text{FastModExp}(b, x-1, n)$, stores the result in $F$, then computes $F' = F \times b$, and returns $F' \bmod n$.

By the inductive hypothesis (since $x-1 < x$),

$$
F = b^{x-1} \bmod n
$$

Therefore, the algorithm returns:

$$
\begin{aligned}
F' \bmod n &= (F \times b) \bmod n \\
&= ((b^{x-1} \bmod n) \times b) \bmod n \\
&= (b^{x-1} \times b) \bmod n \quad \text{(by mod multiplication property**)} \\
&= b^x \bmod n \quad
\end{aligned}
$$

Conclusion:

We showed the algorithm is correct for $x = 0$ (base case), and if it is correct for all $k < x$, then it is correct for $x$ (inductive step).

Thus, by induction on $x$, $\text{FastModExp}(b, x, n)$ correctly returns $b^x \bmod n$ for all $x \geq 0$, with fixed $b > 1$ and $n > 1$.

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
