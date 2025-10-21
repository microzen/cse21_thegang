# Assignment 2

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: October 13 2025

---
### Question 1
(a) (Remember to explain your work.)
Suppose you are giving out candy to trick-or-treaters. There is a group of 10 different trick-or-treaters that come to your door. You must give each of the 10 trick-or-treaters exactly one candy. You have an unlimited supply of 6 different candy bars: Snickers, Milky way, 3 Musketeers, Almond Joy, Twix, Kit Kat.

i. How many different ways can you hand out one candy bar to each of the 10 trick-or-treaters?

There are 6 choices for each person, so the total number of distributions is 

$$6^{10}$$

ii. How many different ways can you hand out one candy bar to each of the 10 trick-or-treaters if you hand out at least one candy bar of each variety?

Count all possible candy distributions with no restrictions:

$$6^{10}$$

Subtract the cases where at least one candy type is not used. Using the Inclusive-Exclusive Principle. The number of valid distributions is 

$$\sum_{k=0}^{6} \binom{6}{k} (6-k)^{10} (-1)^k = \binom{6}{0}6^{10} - \binom{6}{1}5^{10} + \binom{6}{2}4^{10} - \binom{6}{3}3^{10} + \binom{6}{4}2^{10} - \binom{6}{5}1^{10}+\binom{6}{6}0^{10}$$

iii. How many different ways can you hand out one candy bar to each of the 10 trick-or-treaters if you hand out exactly 6 Snickers?

Choose 6 out of the 10 trick-or-treaters to receive Snickers:

$$\binom{10}{6}$$

The remaining 4 each get one of the other 5 candy types:

$$5^4$$

Thus, the total is

$$\binom{10}{6}5^4$$

(b) (Remember to explain your work.) Suppose you are leaving out a bowl of 10 candies to trick-or-treaters. You have an unlimited supply of 6 different candy bars: Snickers, Milky way, 3 Musketeers. Almond Joy, Twix, Kit Kat.

i. How many different ways can you select 10 candies for the bowl (choosing from your assortment of 6 different candies)?

This is a stars and bars problem. Selecting 10 candies from 6 types. The total ways are

$$\binom{10+6-1}{6-1}=\binom{15}{5}$$

ii. How many different ways can you select 10 candies for the bowl so that there is at least one candy bar of each variety?

Place one of each type first, then select the remaining 4 candies freely. The total ways are

$$\binom{4+6-1}{6-1}=\binom{9}{5}$$

iii. How many different ways can you select 10 candies for the bowl so that the bowl has exactly 6 Snickers?

Fix 6 Snickers first, then select 4 more candies from the other 5 types. The total ways are

$$\binom{4+5-1}{5-1}=\binom{8}{4}$$

---

### Question 2
Suppose you are traveling fron the bottom-left corner of a $10 \times 6$ grid of blocks and you wish to get the top-right corrner only using up and right movements:

**a).** How many paths are there from the bottom-left corner to the top-right corner using right and up moves so that you go through at least one of the two blue dots (2,5) and (4,8) in the first picture?

Solution: First, we could go from (1,1) to (2,5), then (2,5) to (6,10), and let it be Plan-A. Also, we could go from (1,1) to (4,8), then (4,8) to (6,10), and let it be Plan-B. Therefore, we got $A\cup B$, which equal to $|A| + |B| - |A \cap B|$. Now we know $|A| = \dbinom{5}{1}\dbinom{9}{4}$ and $|B| = \dbinom{10}{3}\dbinom{4}{2}$ and $|A \cap B| = \dbinom{5}{1}\dbinom{5}{2}\dbinom{4}{2}$, which is the steps that have to pass (2,5) and (4,8).

$$\dbinom{5}{1}\dbinom{9}{4}+\dbinom{10}{3}\dbinom{4}{2}-\dbinom{5}{1}\dbinom{5}{2}\dbinom{4}{2}$$

**b).** How many paths are there from the bottom-left to the top-right corner using right and up moves so that you avoid the green area in the second picture?

Solution: First, all the moves have to avoid the moves pass (3,6) or (3,7). Let Plan-A become the moves that must pass (3,6), and Plan-B become the moves pass (3,7). We got $|\text{ All }| - (|A| + |B| - |A \cap B|)$. 

$$\dbinom{14}{5}-\left(\dbinom{7}{2}\dbinom{7}{4} + \dbinom{8}{2}\dbinom{6}{3}-\dbinom{7}{2}\dbinom{1}{1}\dbinom{6}{3}\right)$$

---

### Question 3
Compute the number of integer solutions for each equation:
(Include a justification)

$$a_1+a_2+a_3+a_4+a_5=50$$

$$ (a)\quad 1 \leq a_1 \\
      \qquad \; 2 \leq a_2 \\
      \qquad \; 3 \leq a_3 \\
      \qquad \; 4 \leq a_4 \\
      \qquad \; 5 \leq a_5 \\ $$
      
remove the lower bounds first, so I can make it :
$$a_1-1 = b_1 \\
a_2-2 = b_2 \\
a_3 - 3 = b_3 \\
a_4 -4 = b_4\\
a_5-5 = b_5 $$
Then, equation should be changed to :
$$ b_1 + b_2 + b_3 + b_4 + b_5 = 50-(1+2+3+4+5) = 35 $$

By using stars and bars, the answer is :
 $$ \binom{35+5-1}{5-1} = \binom{39}{4} =82,251 $$


$$ (b)\quad 0 \leq a_1 \\
      \qquad \; 0 \leq a_2 \\
      \qquad \; 0 \leq a_3 \\
      \qquad \; 0 \leq a_4 \\
      \qquad \; 10 \leq a_5 \leq 20\\ $$

Trying to remove lower bounds first and ignoring upper bounds and take the total.

$$ 10 \leq a_5 \leq 20 \rightarrow b_5 = a_5 - 10, b_5\geq0 \\
\rightarrow a_1+a_2+a_3+a_4+b_5 = 50-10=40$$

now by using stars-and-bars, take the total.
$$ \binom{40+5-1}{5-1} = \binom{44}{4} $$
and subtract the case of $b_5 \geq 11$ :
$$ c=b_5-11,b_5\geq11 \\
\rightarrow b_5 = c + 11 \\
\rightarrow a_1+a_2+a_3+a_4+c=40-11=29 $$
now again by using stars-and-bars, take the case of what we need to subtract.

$$ \binom{29+5-1}{5-1} = \binom{33}{4} $$

now by inclusion-exlcusion, trying to exclude the case of what we need to subtract from total.

$$\binom{44}{4} - \binom{33}{4} = 135,751 - 40,920 = 94,831$$

$$ (c)\quad 0 \leq a_1 \leq 15\\
      \qquad \; 0 \leq a_2 \leq 15\\
      \qquad \; 0 \leq a_3 \leq 15\\
      \qquad \; 0 \leq a_4 \leq 15\\
      \qquad \; 0 \leq a_5 \leq 15\\ $$

Firstly, take the total by using stars-and-bars.
$$\binom{50+5-1}{5-1} = \binom{54}{4}$$

and now using inclusion-exclusion, and trying to exclude one or more $ a_i > 15$.
*  one : subtract
$$\binom{5}{1} \binom{38}{4} = 5\binom{38}{4} $$
* two : add back because of over subtraction correction
$$\binom{5}{2} \binom{22}{4} = 10\binom{22}{4} $$
* three : intersctions subtract again
$$\binom{5}{3} \binom{6}{4} = 10\binom{6}{4}$$

$$\rightarrow \binom{54}{4} - 5\binom{38}{4} + 10\binom{22}{4} - 10\binom{6}{4} = 316,251 - 369,075 + 73,150 - 150 = 20,176 $$

---

### Question 4

**a)**. $\forall n \ge 0$, consider the identity: 

$$\dbinom{n+2}{3} = (1)(n)+(2)(n-1)+(3)(n-2)\dots+(n-1)(2)+(n)(1)$$

Prove the identity combinatorially by counting the same set in two different ways or by counting two different set and establishing a bijection between them.

Solution:

We want to prove that both sides of the equation counts the same set, which is the number of ways to choose 3 positions for 1's in a binary string length $n+2$

LHS: $\dbinom{n+2}{3}$ equals to the number of ways to choose 3 positions for number "1" in a birary string length $n+2$.

RHS: Assume it also counts the number of ways to choose 3 positions for number "1" in a binary string length $n+2$ 

Call 3 positions of number "1" a,b,c $(a\lt b\lt c)$

Assume middle position, $b=m$, so left position (a) and right position (b) of $m$ must be reserved. We got $2 \le m\le n + 1$ or $2 \le b\le n+1$. Also, 

$$1\le a\le m-1$$ 

$$m+1\le c\le n+2$$

For a fixed $b$, there are $(m-1)[(n+2)-m]$ choices to pick position a and c to form the binary strings:

$$\sum_{m=2}^{n+1} (m-1)\left((n+2) -m \right)$$

Let $x=m-1$, equation becomes

$$\sum_{x=1}^{n}x(n+1-x)=(1)(n)+(2)(n-1)+\dots+(n)(1)$$

$$\sum_{x=1}^{n}x(n+1-x)=RHS$$

So both sides count the same set.

Proved

**b).** $\forall n \ge 0$, consider the identity:

$$P(n,k)=P(n-1,k)+kP(n-1,k-1)$$

Prove the ideneity combinatorially by counting the same set in two different ways or by counting two different sets and establishing a bijection between them.

Solution:

We want to prove that both sides of the equation counts the number of ways we can choose k distinct balls chosen from a set of n balls to fit in k indistinguishable boxes which can only store 1 ball.

LHS: $P(n,k)$ = number of ways we can choose k distinct balls chosen from a set of n balls to fit in k indistinguishable boxes which can only store 1 ball.

RHS: 
+ We start with $P(n-1, k)$ = number of ways to fit distinct balls chosen from the same set of n balls but without ball n (so it's picking from n-1 balls) into k indistinguishable boxes which can only store 1 ball

+ For $kP(n-1, k-1)$, this is the number of ways to fit distinct balls chosen from the same set of n balls but must always include ball n (so the rest of balls is still picking from n-1 balls) into k indistinguishable boxes which can only store 1 ball

RHS is $P(n-1,k)$ and $kP(n-1,k-1)$ combining together, forming the number of ways we can fit k distinct balls from a set of n balls into k boxes that can only store 1 ball whether ball n is present or not.

Therefore, RHS is counting the same set as LHS.

Proved.
