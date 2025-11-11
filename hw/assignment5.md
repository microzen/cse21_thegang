# Assignment 5

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: November 10 2025

---

### Question 1
Consider the following algorithm $\textit{Factorial}$ that takes as input $n$ and returns the value of $n!$.

$\textit{Factorial( n)}$\
1.$\text{ fact = 1}$\
2.$\text{ for }$ $i$ = 1..$n$:\
3.$\text{ fact = fact*}$ $i$\
4.$\text{return fact}$

(a) Consider the loop invariant:
$\text{After t iterations, fact = t!}$\
Prove that this loop invariant is correct by induction.

*Proof by induction

1.initialization ( t = 0 )
* Before loop starts, code set is fact = 1. Which is 0! = 1, so after 0 iteration, fact = 1 = 0!.

2.Induction step
* Assume that after t iterations the invariant hold ( fact = t! ) and during the (t+1) iterations the loop multiply by t+1.\
$fact = t! * (t+1) = (t+1)!$
after t+1 iterations the invariant still holds.

By Induction, the invariant 'After t iterations, fact = t!' holds for all t = 0,1,2,...,n.

(b) Use the loop invariant to show that the algorithm is correct.

* The loop executes exactly n iterations (for i = 1,2,3,...,n), applying t = n we have fact = n! after loop finishes, then we have return fact, so it returns n!.
Therefore, the algorithm is correct.

---

### Question 2 

Consider the following sorting algorithm that takes a list of integers as an input and outputs a sorted list of those elements. (All you need to know about MERGE is that it takes two sorted lists of integers and returns a sorted list of all the integer combined. if the size of lists are j and k, then the runtime of MERGE is O(k + j).)

```code
QueueSort(a_1, ... a_n)
    Initialize a queue Q of lists so that each element of the input is in a list all by itself.
    Q = ([a_1], [a_2], ... ,[a_n])
    while |Q| >= 2:
        dequeue the first two lists from Q and MERGE the two lists together.
        enqueue the result into Q
    return Q
```
Consider the loop invariant:
$$\text{After each iteration, every list in Q is sorted.}$$

**a).** Prove this loop invariant using induction.

**Base Case**: Before the iteration start, $Q = \{[a_1],[a_2],\dots [a_n]\}$. Every single list has only one element and it is sorted in Q since there is only one element. Thus, the loop invariant hold true at initialization.

**Inductive Hypothesis**: Let $k \ge 1$. Assume after k iteration, every list in Q is sorted.

**Inductive Step**: To show at $k+1$ iteration, every list in Q is sorted:

By Inductive Hypothesis, the first list and second list are sorted lists in Q after k iteration. Therefore, at $k + 1$ iteration, These two lists at the beginning of queue are dequeued, and other remained lists in Q are sorted. The MERGE function will merge them correctly into one sorted list. After that, the new sorted list will be enqueued into Q; and every list in Q is sorted.

Conclusion, All lists in Q is sorted at the end of $k+1$ iteration.


**b).** Use the loop invariant to show that the algorithm is correct.

The while loop continues unitl as long as $|Q| \ge 2$, the loop terminate occurs at $|Q| \le 2$. Since all lists in Q is sorted at the end of any iteration, it is also true at the loop terminates. After that, the $|Q| = 1$ and every list in Q is sorted. Therefore, the only one sorted list in Q will be return, the algrithm is correct.


**c).** Use the runtime method we learned in class to show that this algorithm runs in $O(n^2)$.

For all the $|Q| = n$, each time it will dequeue 2 lists and enqueue 1 list to the end of Q. Therefore, the while loop will run in $n - 1$ time.

For all MERGE function, the worst case of MERGE functions is $O(k+j)$, which is given by the question; and it occurs inside of the loop.

Therefore, combine these 2 situation, the run time for this algorithm is $O(n^2)$


**d).** Show that $O(n^2)$ is not a tight bound by doing a more careful analysis.

For this algorithm, each MERGE function takes $O(j + k)$ in run time. 

To shows that, we separate the MERGEs into levels.

 The first level, $Q = \{[x], [x], \dots [x]\}$ has n lists of size 1.

The second level, $Q = \{[x,y], [x,y], \dots [x,y]\}$ has $\displaystyle\frac{n}{2}$ lists of size 2.

The third level, $Q = \{[x,y,w,z], [x,y,w,z], \dots [x,y,w,z]\}$ each has $\displaystyle\frac{n}{4} $ lists of size 4.

The k level has 1 list of size n.

We need to find k: $n, \displaystyle\frac{n}{2}, \displaystyle\frac{n}{4},...,\displaystyle\frac{n}{2^k}$

We know that $\displaystyle\frac{n}{2^k} = 1$
$$ n = 2^k$$
$$ k = \log_2(n)$$

So the algorithm runtime can be found by:

O(number of layers)*O(time of merge)

$= O(\log(n))\cdot O(n)$

$= O(nlog(n))$, which is better than $O(n^2)$.

Therefore, $O(n^2)$ is not a tight bound

---

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

Solution:

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

---

### Question 4
For each situation below, first give the recurrence for the runtime of the algorithm (no
explanation for this part.) Then use the Master Theorem, if possible, and give the values for a b and d and the O bound.

a) Suppose an algorithm solves a problem of size n by recursively calling 2 subproblems each of size $2n/5$. Then the non-recursive part of the algorithm takes $O(n^2)$ time.

Solution:

Recurrence:

$f(n) = 2f(\displaystyle\frac{2n}{5}) + O(n^2)$

Master Theorem:

a = 2, b = 5/2, d = 2

$a < b^d$

$T(n) = O(n^2)$

b) Suppose an algorithm solves a problem of size n by recursively calling 2 subproblems each of size n/4. Then the non-recursive part of the algorithm takes $O(\sqrt{n})$ time.

Solution: 

Recurrence:

$f(n) = 2f(\displaystyle\frac{n}{4}) + O(\sqrt{n})$

Master Theorem:

a = 2, b = 4, d = 1/2

$a = b^d$

$T(n) = O(n^{0.5}\log{n})$

c) Suppose an algorithm solves a problem of size n by recursively calling 2 subproblems each of size
n/4. Then the non-recursive part of the algorithm takes $O(n^{1.5})$ time.

Solution:

Recurrence:

$f(n) = 2f(\displaystyle\frac{n}{4}) +O(n^{1.5})$

Master Theorem:

a = 2, b = 4, d = 1.5

$a < b^d$

$T(n) = O(n^{1.5})$
