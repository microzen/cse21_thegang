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

**Base Case**: Before the iteration start, $Q = \{[a_1],[a_2],\dots [a_n]\}$. Every single list has only one element and it is sorted in Q since only one element. Thus, the loop invariant hold true at initialization.

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

For this algorithm, each MERGE function takes $O(l + k)$ in run time. As the loop until the end, it approaches $O(n\ log_2(n))$

To shows what, the each MERGE in the first level, $Q = \{[1], [1], \dots [1]\}$ each merged action costs $\frac{n}{2} \times O(2)$. It merges the (n/2) elements, that include lists all in 1 size, in Q.

The second level, $Q = \{[1,2], [1,2], \dots [1,2]\}$ each costs $\frac{n}{4} \times O(4)$. It merges the (n/4) elements, that include lists all in 2 size, in Q.

The third level, $Q = \{[1,2,3,4], [1,2,3,4], \dots [1,2,3,4]\}$ each costs $\frac{n}{8} \times O(8)$. It merges the (n/8) elements, that include lists all in 4 size, in Q.

At n (last) level, it megers $\frac{n}{2^k}$, which approch to 2 elements, that include lists all in n size, in Q.

Therefore, we start with lists of size 1 and double the size until we reach $n = (1, 2, 4, 8, ..., n)$. This requires $log_2(n)$ passes. The total run time is $O(n\ log_2(n))$

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

(a) Consider the loop invariant:
$\text{After t iterations, fact = t!}$\
Prove that this loop invariant is correct by induction.

1.initialization ( t = 0 )
* Before loop starts, code set is fact = 1. By definition 0! = 1, so after 0 iteration, fact = 1 = 0!. The invariant holds initially,

2.Inductive hypothesis
* Asuum that after $t$ iterations, fact = $t!$.

3.Inductive step ( t $\rightarrow$ t+1)
* during the (t+1) iterations the loop multiply by t+1.\
Using the hypothesis fact = $t!$, and we get

$fact = t! * (t+1) = (t+1)!$
after t+1 iterations the invariant still holds.

By Induction, the invariant 'After t iterations, fact = t!' is true.

(b) Use the loop invariant to show that the algorithm is correct.

1.initialization
* Before the loop start, fact = 1.
By definition 0! = 1, so the invariant fact = t! holds for $t$ = 0.

2.Maintencance
* From part(a), I proved that if the invariant holds after $t$ iterations, then it also holds after $t+1$ iterations too because the invariant is true initially and is maintained from $t$ to $t+1$.
By mathematical induction it holds for all $t \in$ {0,1,...n}.

3.Termination
* When the loop finishes, $t=n$.
By the invariant, we have fact = $n!$.
The algorithm then executes retunr fact, so it correctly returns $n!$.
