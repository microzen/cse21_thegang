# Assignment 5

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: October 27 2025


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