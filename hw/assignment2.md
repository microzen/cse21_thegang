# Assignment 2

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: October 13 2025

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