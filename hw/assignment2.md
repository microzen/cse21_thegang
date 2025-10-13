# Assignment 2

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: October 13 2025

---

### Question 1.a)
Suppose you are giving out candy to trick-or-treaters. There is a group of 10 different trick-or-treaters that come to your door. You must give each of the 10 trick-or-treaters exctly one candy. You have an unlimited supply of 6 different candy bars: Snickers, Miky way, 3 Musketeers, Almond Joy, Twix, Kit Kat.

**i).** How many different ways can you hand out one candy bar to each of the 10 trick-or treaters?

Solution: we can treat this as 10 spaces(trick-or-treaters) and put the numbers(candy) 1 to 6 into there. Therefore, we got 6 to the power 10 way to do that.

$$(6)^{10}$$

**ii).** How many different ways can you hand out one candy bar to each of the 10 trick-or-treaters if you hand out at least one candy bar of each variety?

Solutioin: 

**iii).** How many different ways can you hand out one candy bar to each of the 10 trick-or-treaters if you hand out exaclty 6 Snickers?

Solution: handing out excalty 6 Snickers means you have 6 fixed trick-or-treaters received Snickers, which is 10 pick 6. Also, the remains(4 trick-or-treaters) received random one from other 5 types of candy, which is 5 to the power 4.

$$(10C6)(5^4)=\frac{(10!)}{6!(10-6)!}\times(5^4)$$

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

LHS: $\dbinom{n+2}{3}$ equals to the number of way to choose 3 positions for 1's in a birary string length $n+2$.

Call 3 positions of 1 a,b,c $(a\gt b\gt c)$

Assume middle position, $b=m$, left position and right position of $m$ must be reserved. We got $2 \le m\le n + 1$ or $2 \le b\le n+1$. Also, $1\le a\le m-1, m+1\le c\le n+2$

For a fixed $b$, there are $(m-1)[(n+2)-m]$ choices:

$$\sum_{m=2}^{n+1} (m-1)\left((n+2) -m \right)$$

Let $x=m-1$, equation becomes

$$\sum_{x=1}^{n}x(n+1-x)=(1)(n)+(2)(n-1)+\dots+(n)(1)$$

$$\sum_{x=1}^{n}x(n+1-x)=RHS$$

Proved

**b).** $\forall n \ge 0$, consider the identity:

$$P(n,k)=P(n-1,k)+kP(n-1,k-1)$$

Prove the ideneity combinatorially by conting the same set in two different ways or by counting two different sets and establishing a bijection between them.

Solution:
LHS: $P(n,k)$ = number of k-length strings formed by distinct elements chosen from a set of n-elements.
RHS: 
+ We start with $P(n-1, k)$ = k-length strings formed by distinct elements chosen from the same set of n elements but without element n (so it's a set of n-1 elements)
+ For $kP(n-1, k-1)$, this is the number of ways we can count k-length strings that definitely contains element n. There are k ways to pick a position for element n, and there are k - 1 positions msut be filled with different elements from remaining elements in the set of n elements, which is actually a set of n-1 elements now.

RHS is $P(n-1,k)$ and $kP(n-1,k-1)$ combining together, forming the number of ways we can count k-length strings whether element n is present or not.

Therefore, RHS is counting the same set as LHS.

Proved.
