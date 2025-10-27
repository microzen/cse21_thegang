# Assignment 3

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: October 27 2025

### Question 1
Suppose you are leaving out a bowl of 10 candies to trick-or-treaters. You have an unlimited
supply of 6 diﬀerent candy bars: Snickers, Milky way, 3 Musketeers, Almond Joy, Twix, Kit Kat. You don’t really know what candies to give out so you use a random sampling process to select the candies:

You roll a 6-sided die ten times in a row. If you roll a 1, you put a Snickers in the bowl, if you roll a 2, you put a Milky Way in the bowl, if you roll a 3, you put a 3 Musketeers in the bowl, if you roll a 4, you put an Almond Joy in the bowl, if you roll a 5, you put a Twix in the bowl and if you roll a 6, you put a Kit Kat in the bowl.

**(a).** What is the expected number of varieties of candies that don’t get selected using the sampling method above?

Let $E(X) = E(X_1) + E(X_2) + \dots + E(X_6)$, which means the expectation of not rolling 1, or 2, or 3, or 4, or 5, or 6. Set:

$$X_i = \begin{cases}
   1 &\text{if - not rolling any die of i} \\
   0 &\text{if otherwise} 
\end{cases}$$

We know, $E(X_i) = P(X_i = 1)$, repersents the probability of not rolling i. Therefore, 

$$P = \frac{\text{ None of one of i type in rolling 10 times }}{\text{ All the outcome in rolling 10 times}} = \frac{5^{10}}{6^{10}}$$

Thus, $E(X) = E(X_1) + E(X_2) + \dots + E(X_6)$, we got:

$$E(X) = (6)E(X_i) = (6)\frac{5^{10}}{6^{10}} \\
\approx 0.969$$

**(b).** What is the expected number of varieties of candies that don’t get selected using a uniform random sampling?

For a uniform random sampling, we focus on the uniform combinations, for example, rolling dies 1, 1, 2, 3, 4, 5 is the same with rolling 1, 2, 3, 4, 5, 1 because the outcome of these sitiation should be count once only.

Therefore, total combination outcome should be $\dbinom{n + k - 1}{k - 1} = \dbinom{15}{5}$.

Since there is no $i$ be rolled, the first bar is fixed at the beginning of the Stars and Bars. As the result, the outcome without any of rolling die $i$ is $\dbinom{n + (k - 1) - 1}{(k -1) -1} = \dbinom{14}{4}$.

Let:

$$X_i = \begin{cases}
   1 &\text{if - not rolling any die of i} \\
   0 &\text{if otherwise} 
\end{cases}$$

and, 
$$E(X) = E(X_1) = E(X_2) + \dots + E(X_6)$$

We known,
$$E(X_i) = P(X_i = 1) = \frac{\dbinom{14}{4}}{\dbinom{15}{5}} = \frac{1}{3}$$

Got, 

$$E(X) = (6)E(X_i) = (6)\frac{1}{3} = 2$$


**(c).** What is the expected number of varieties of candies that you have exactly one of using this sampling method?

Exactly one means when we $i$ is rolled, the outcome for other 5 rollings should be in the set with out $i$. For examle, if 1 is rolled the set of rolling for others should be $\{2, 3, 4, 5, 6\}$. Therefore, outcome of exaclty one is $(10)(5^9)$.

Let: $E(X) = E(X_1) + E(X_2) + \dots + E(X_6)$, and

$$X_i = \begin{cases}
   1 &\text{if - exactly one rolling of i} \\
   0 &\text{if - otherwise} 
\end{cases}$$

We know, $E(X_i) = P(X_i = 1) = \frac{(10)(5^9)}{6^{10}}$

$$E(X) = (6)E(X_i) = (6)\frac{(10)(5^9)}{6^{10}} \approx 1.938$$


(d) What is the expected number of varieties of candies that you have exactly one of using a uniform random sampling method?

The outcome of exactly one for combinations could be treated as fixed the 0 and 1 at the first 2 position of the Bars. So, (n - 1) by fixed 0, and (k - 1) by fixed 1. Therefore, the outcome of exactly one is $\dbinom{(n - 1) + (k -1) - 1}{(k - 1)} = \dbinom{13}{4}$.

Let: $E(X) = E(X_1) + E(X_2) + \dots + E(X_6)$, and

$$X_i = \begin{cases}
   1 &\text{if - exactly one rolling of i} \\
   0 &\text{if - otherwise} 
\end{cases}$$

We know, $E(X_i) = P(X_i = 1)$, thus,

$$E(X_i) = \frac{\dbinom{13}{4}}{\dbinom{15}{5}}$$

$$E(X) = (6)E(X_i) = (6)\frac{\dbinom{13}{4}}{\dbinom{15}{5}} \approx 1.429$$

### Question 3
a) What is the expected number of swaps in the first iteration of Bubble Sort (when i = 1)?

 Solution:
Let E(x) = expected number of swaps in the first iteration of Bubble Sort.

This is a uniform distribution because the probability that it needs 1 swap is the same as
the probability that it needs 2 swaps, or k swaps.

There are n different number of swaps possible for the first iteration, from 0 swaps to n - 1 swaps.

Therefore, the probability that the list needs k swap is the same and equal to $\displaystyle\frac{1}{n}$ $\text{ }(\forall \text{ }0 \leq k \leq n - 1)$

$$E(x) = \displaystyle\sum_{r=0}^{n - 1}P(X=r)r$$

 $$= \displaystyle\sum_{r=0}^{n - 1}\displaystyle\frac{1}{n}\cdot r$$
 $$= \displaystyle\frac{1}{n}\cdot\displaystyle\sum_{r=0}^{n - 1}r$$
 $$= \displaystyle\frac{1}{n}\cdot\frac{(n - 1  + 0)n}{2}$$
 $$= \displaystyle\frac{n - 1}{2}$$

 So the expected number of swaps for an array of n elements is $\text{ }\displaystyle\frac{n - 1}{2}$

 b) A permutation is called a one-pass permutation if it is completely sorted after one pass of bubble
sort (one iteration of the outer loop.) For example, [3,1,2,4,5] is a one-pass permutation of length
5. 

(Note: we will consider the increasing permutation, e.g. [1,2,3,4,5], as a one-pass permutation
since it is technically sorted after one pass even though there are no swaps.)


Determine a formula for the number of one-pass permutations of length n.


(Hint: enumerate the number of one-pass permutations for n = 1, 2, 3, 4 and see if there is a
pattern. Then try to justify your pattern.)

Solution:

n = 1 has 1 one-swap permutation

n = 2 has 2 one-swap permutations

n = 3 has 4 one-swap perumations

n = 4 has 8 one-swap permutations

We can see that the formula is $2^{n-1}$.

Prove: An array of n elements has n - 1 pairs formed by 2 consecutive elements. Each pair has 2 options: swap or no swap. The number of ways all these pairs are swapped/not swapped formed together is essentially how many ways of swapping elements that 1 pass of the Bubble Sort can do to that array. Therefore, the number of permutations that can be sorted in 1 pass is $2^{n - 1}$, with "2" is the number of options for each pair, and "n - 1" is the number of pairs formed by 2 consecutive elements in that array.
