# Assignment 4

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

---

### Question 2
A person (patient 0) is infected with the zombie virus.
There is a 4/9 chance that an infected person turns into a zombie. Once a person turns into a zombie, it will infect 2 other people before it dies.

**(a).** Including the first person who was infected, what is the expected number of infected people (zombie or not zombie)?

Let E(I) be the expected total number of infected people (including Patient 0). We can find E(I) using the Law of Total Expectation by conditioning on Patient 0's outcome.

1. Case 1: Patient 0 becomes a zombie (Prob = 4/9)The count is 1 (Patient 0) plus the expected infections from the 2 new people they infect.
$E(I | \text{Zombie}) = 1 + E(I) + E(I) = 1 + 2E(I)$

2. Case 2: Patient 0 does not become a zombie (Prob = 5/9)The count is 1 (Patient 0), and the process stops.
$E(I | \text{Not Zombie}) = 1$

Combining these cases:

$$E(I) = (4/9) \cdot (1 + 2E(I)) + (5/9) \cdot (1)$$

$$E(I) = 4/9 + (8/9)E(I) + 5/9$$

$$E(I) = 1 + (8/9)E(I)$$

$$(1/9)E(I) = 1$$

$$E(I) = 9$$

The expected number of infected people is 9.

**(b).** What is the expected number of zombies?

Let E(Z) be the expected total number of zombies.
1. Case 1: Patient 0 becomes a zombie (Prob = 4/9). The count is 1 (Patient 0) plus the expected zombies from the 2 new people.
$E(Z | \text{Zombie}) = 1 + E(Z) + E(Z) = 1 + 2E(Z)$

2. Case 2: Patient 0 does not become a zombie (Prob = 5/9). The count is 0, and the process stops.
$E(Z | \text{Not Zombie}) = 0$

Combining these cases:

$$E(Z) = (4/9) \cdot (1 + 2E(Z)) + (5/9) \cdot (0)$$

$$E(Z) = 4/9 + (8/9)E(Z)$$

$$(1/9)E(Z) = 4/9$$

$$E(Z) = 4$$

The expected number of zombies is 4.

**(c).** What is the probability that there are exactly 3 zombies?

Let $P_k$ be the probability that exactly $k$ zombies originate from one infected person. We need to find $P_3$.

We can define $P_k$ recursively:
- $P_0 = P(\text{Not Zombie}) = 5/9$
- For $k \ge 1$, Patient 0 must become a zombie (Prob 4/9) and the 2 new infected people (A and B) must produce a combined $k-1$ zombies.
$P_k = (4/9) \cdot \sum_{i=0}^{k-1} (P_i \cdot P_{k-1-i})$

Now, we calculate step-by-step:

$P_0 = 5/9$

$P_1 = (4/9) \cdot (P_0 \cdot P_0)$

$P_1 = (4/9) \cdot (5/9) \cdot (5/9) = 100/729$

$P_2 = (4/9) \cdot (P_1 \cdot P_0 + P_0 \cdot P_1) = (4/9) \cdot (2 \cdot P_0 \cdot P_1)$

$P_2 = (4/9) \cdot 2 \cdot (5/9) \cdot (100/729) = 4000/59049$

$P_3 = (4/9) \cdot (P_2 \cdot P_0 + P_1 \cdot P_1 + P_0 \cdot P_2) = (4/9) \cdot (2 \cdot P_0 \cdot P_2 + P_1^2)$

$P_3 = (4/9) \cdot \left( 2 \cdot (5/9) \cdot (4000/59049) + (100/729)^2 \right)$

$P_3 = (4/9) \cdot \left( 40000/531441 + 10000/531441 \right)$

$P_3 = (4/9) \cdot (50000 / 531441)$

$P_3 = 200000 / 4782969$

The probability of exactly 3 zombies is approximately $4.18\%$.

---

### Question 3
**a)** What is the expected number of swaps in the first iteration of Bubble Sort (when i = 1)?

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


** b)** A permutation is called a one-pass permutation if it is completely sorted after one pass of bubble sort (one iteration of the outer loop.) For example, [3,1,2,4,5] is a one-pass permutation of length 5. 

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

---

### Question 4

For each algorithm, compute the exact number of times the algorithm prints in terms of n where n $\ge$ 3. (We use the convention that if there is a for loop such that the starting value is greater than the ending value, then that loop does not run and for loops include both endpoints.)

**(a)**
```python
for i = 1 to n:
   for i = 0 to n -1:
         print(i, j)
```

Values are i, i+1, i+2. for each fixed i, the inner loop prints 3 times. i goes from 1 to n, so there are n choices of 1. Each choice contributes 3 prints

Answer : 3n

**(b)** 
```python
for i = 0 to n - 1:
   for j = i to 2^i:
      print(i, j)
```

j runs from 1 to $2^i$, $2^i$ prints for that i.

$$\rightarrow 1+2+4+ ... + 2^{n-1} $$

Sum over all i then total prints will be $\sum_{i=0}^{n-1} 2^i.$

* Answer: $\sum_{i=0}^{n-1} 2^i$

**(c)**
```python
for i = 3 to n:
   for j = 2 to i - 1:
      for k = 1 to j - 1:
         print(i, j, k)
```

- Exapnding the loops mathematically then : $\sum_{i=3}^{n} \sum_{j=2}^{i-1} \sum_{k=1}^{j-1} 1$
$$\rightarrow \sum_{k=1}^{j-1} 1 = j-1$$

$$\rightarrow \sum_{i=3}^{n} \sum_{j=2}^{i-1}(j-1)$$

$$\rightarrow \sum_{j=2}^{i-1}(j-1) = \sum_{j=1}^{i-2}j$$

$$\rightarrow \sum_{i=3}^{n} \sum_{j=1}^{i-2}j$$

equation 1: $\sum_{i=1}^{n}i = \frac{n(n+1)}{2}$ by using this equtions, we can make

$$\sum_{i=3}^{n}\frac{(i-2)(i-1)}{2} = \sum_{i=1}^{n}\frac{(i-2)(i-1)}{2}-\frac{(2-2)(2-1)}{2}-\frac{(1-2)(1-1)}{2}$$

since i=1 and i=2 will be cancled out, we'll get $\sum_{i=1}^{n}\frac{(i-2)(i-1)}{2}$ and we can expand the equation.

$$\rightarrow \frac{1}{2}\sum_{i=1}^{n}(i^2-3i+2) = \frac{1}{2}(\sum_{i=1}^{n}i^2-3\sum_{i=1}^{n}i+2\sum_{i=1}^{n}1)$$

equation 2: $\sum_{i=1}^{n}i^2 = \frac{n(n+1)(2n+1)}{6}$ by using this equtions, we can make:

$$\frac{1}{2}(\frac{n(n+1)(2n+1)}{6}-3(\frac{n(n+1)}{2})+2n)$$

$$= \frac{1}{12}(n(n+1)(2n+1)-9n(n+1)+12n) = \frac{n}{12}((n+1)(2n+1)-9(n+1)+12)$$

$$= \frac{n}{12}(2n^2+n+2n+1-9n-9+12) = \frac{n}{12}(2n^2-6n+4) = \frac{n}{6}(n^2-3n+2)$$

now, we did all algebra and simplify and take an answer

Answer:

$$\frac{n(n-1)(n-2)}{6}$$
