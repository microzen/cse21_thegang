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
