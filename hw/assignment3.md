# Assignment 3

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: October 20 2025

### Question 1
Partnership Dominos is a game that involves 4 players and a Double-6 Domino set.

A Double-6 Domino set is a set of 28 different tiles such that each tile hase two values (one one each side. The values are given by a number of pips or dots to signify the value.) There is one domino for each combination of values from 0 through 6 (including doubles). At the start of round, each of the 4 players (North, South, East, West) gets 7 tiles.

**a).** What is the probability that North has the double-six tile (the tile with 6 pip on either side) in their opening hand?

Solution: North player has 7 chances to have his tiles in the opening hand. Since the probability to have double-six is $\frac{1}{28}$, thus, the probability of having double-six in the opening is $\frac{1}{28}+\frac{1}{28}+\dots+\frac{1}{28}$ seven times.

$$\frac{7}{28} = \frac{1}{4}$$


**b).** What is the probability that North has at least one double in their opening hand?

Solution: Base on the formual $P(E)=\frac{|E|}{|S|}$, let's set the $E$ as the outcome of no double in opening hand. Set $S$ as the outcome of having tiles.

1. For E, chose 7 from the other $28 - 7$, which means the 7 pairs out of the total. Thus, $E = \dbinom{21}{7}$
2. For S, chose 7 from 28, thus, $S= \dbinom{28}{7}$
3. Now, the probability of least one double in opening hand is (1 - the probability of no double).

$$P(E) = 1 - \frac{\text{the outcome of no double}}{\text{the outcome of 7 chance having tiles}}$$

$$P(E)=1 - \frac{\dbinom{21}{7}}{\dbinom{28}{7}}$$


**c).** What is the probability that North and South together hold all 7 tiles containing the value 6?

Solution: Total tiles North and South have is 14, so let set space as the outcome of having 14 tiles from 28.

Now, the 7 tiles containing the value 6 is inclueded in the space. Let's set E as the is the remaning 7 tiles from 21.

$$P(E)=\frac{\dbinom{7}{7}\dbinom{21}{7}}{\dbinom{28}{14}}$$


**d).** Suppose that you are player North and you hold 4 of the 7 tiles with the number 6: (6,6),(6,4),(6,2),(6,1) (along with 3 other tiles without 6). What is the probability that your partner (player South) holds the remaining 3 tiles with the number 6: (6,5),(6,3),(6,0)?

Solution: Since North already recived 7 tiles, there are 21 tiles left. South drows 7 tiles form these 21. Among then, 3 must be the remaining 6 tiles, 4 could be random.

$$P(E) = \frac{\dbinom{3}{3}\dbinom{18}{4}}{\dbinom{21}{7}}$$

**e).** A “Bad hand” is a set of 7 dominos with at least four doubles. What is the probability that one of the players has a bad hand?

Solution: 
1. To set |S| as all the outcome of having 7 tiles, which is $\dbinom{28}{7}$
2. To set |E| as least four double means, only 4 pairs + only 5 pairs + only 6 pairs + only 7 pairs.

We got: 

$$P(E) = \frac{\sum_{i=4}^7 \dbinom{7}{k}\dbinom{21}{7-k}}{\dbinom{28}{7}}$$

Now, we got the probability of one person got bad hand. Times 4 is the probability of 4 people got bad hand.

$$P(E) = \frac{4}{\dbinom{28}{7}}\sum_{i=4}^7 \dbinom{7}{k}\dbinom{21}{7-k}$$

**f).** What is the expected number of doubles North will get in their opening hand?

Solution: Let's set $x = \begin{cases}
   1 &\text{if - it is double} \\
   0 &\text{if - it is no double} 
\end{cases}$

We konw $E(X_i) = P(X = 1)$

$$P(X=1) = \frac{7}{28} = \frac{1}{4}$$

Then, 

$$E(X) = E(X_1) + E(X_2) + \dots + E(X_7)$$

$$E(X) = \sum_{i=1}^7 E(X_i)$$

$$E(X) = \frac{7}{4}$$

**g).** What is the expected sum of pips North will have in their hand? (Hint: the total sum of all pips for all 28 tiles is 168)

Solution: Let's set the $X(S) = {0,1,2,3\dots 12}$, which means the a signal tile could be 0 to 12 pips.

$$E(X_i) =  \sum_{r\in X(S)} P(X=r)r$$

We know, there is 1 of zero-pip, 1 of one-pip, 2 of two-pip, 2 of three-pip, 3 of four-pip, 3 of five-pip, 4 of six-pip, 3 of seven-pip, 3 of eight-pip, 2 of nine-pip, 2 of ten-pip, 1 of eleven-pip, 1 of twelve-pip.

So we got:

$$E(X_i) = 0\frac{1}{28} + 1\frac{1}{28} + 2\frac{2}{28} + 3\frac{2}{28}+\dots +12\frac{1}{28}$$

$$E(X_i) = \frac{168}{28}=6$$

Now we need to find $\sum_{i=1}^7 E(X_i)$

$$E(X) = \sum_{i=1}^7 6 = 42$$

---

### Question 2

**(a)** (Remember to explain your work.)

Suppose you are giving out candy to trick-or-treaters. There is a group of 10 diﬀerent trick-or-treaters that come to your door. You must give each of the 10 trick-or-treaters exactly one candy. You have an unlimited supply of 6 diﬀerent candy bars: Snickers, Milky way, 3 Musketeers, Almond Joy, Twix, Kit Kat. You don’t really know what candies to give out so you use a random sampling process to select the candies:

For each trick-or-treater, you roll a 6-sided die. If you roll a 1, you give that trick-or-treater a Snickers, if you roll a 2, you give them a Milky Way, if you roll a 3, you give them a 3 Musketeers, if you roll a 4, you give them an Almond Joy, if you roll a 5, you give them a Twix and if you roll a 6, you give them a Kit Kat.

**a) i.** Using this sampling process, what is the probability that you gave out at least one candy of each type?

Solution: 
1. Set |S| equal to the all the outcome to distribute candies, which is $6^{10}$.
2. Set |E| equal to the outcome of at least one candy of each type, which is $\sum_{i=0}^{6} (-1)^i \dbinom{6}{i}(6-i)^{10}$

Thus,

$$P(E) = \frac{1}{6^{10}}\sum_{i=0}^{6} (-1)^i \dbinom{6}{i}(6-i)^{10}$$

**a) ii.** Using this sampling process, what is the probability that exactly 6 of the trick-or-treaters get a Snickers?

Solution:
1. Set |S| equal to all the outcome to distribute candies.
2. Set |E| equal to the outcome of exactly 6 of the trick-or-treaters get a Snickers

$$|E| = \dbinom{}{}$$

**a) iii.** Explain why this is a uniform random sampling.

Solution: 

---

**(b)** (Remember to explain your work.)

Suppose you are leaving out a bowl of 10 candies to trick-or-treaters. You have an unlimited supply of 6 diﬀerent candy bars: Snickers, Milky way, 3 Musketeers, Almond Joy, Twix, Kit Kat. You don’t really know what candies to give out so you use a random sampling process to select the candies:

You roll a 6-sided die ten times in a row. If you roll a 1, you put a Snickers in the bowl, if you roll a 2, you put a Milky Way in the bowl, if you roll a 3, you put a 3 Musketeers in the bowl, if you roll a 4, you put an Almond Joy in the bowl, if you roll a 5, you put a Twix in the bowl and if you roll a 6, you put a Kit Kat in the bowl.

**b) i.** Explain why this is not a uniform random sampling.

Solution:

**b) ii.** Which outcome (or outcomes) are the least likely to occur? (and why)

Solution:

**b) iii.** (Note: this next part is not using the dice rolls as a sampling process.)

If you used a uniform random sampling process for selecting 10 candies to put in the bowl, then what is the probability that you put at least one of each candy type?

Solution:

### Question 3
You are on a quest and you arrive at 3 trolls (Troll A, Troll B, Troll C)
each standing in front of a door (door A, door B, door C). You know that one troll tells the truth all
the time another troll tells the truth with a probability of 1/2 and lies with a probability of 1/2 and
another troll tells the truth with a probability of 3/4 and lies with a probability of 1/4.
You don’t know which troll is which. The door behind the truthful troll goes to the next quest and
the doors behind the other two trolls send you back to the beginning.
You wish to determine which troll is telling the truth and you get to ask 5 questions to any of the
trolls.
You decide to ask 5 obvious questions to Troll A and learn that Troll A told the truth all 5 times.

**(a).** What is the probability that Troll A is the truthful troll? (Troll A tells the truth all the time.)

Solution:

Define: Troll **Honest** tells the truth 100% of times (P(Honest) = 1), troll **Half** tells the truth 50% of times (P(Half) = 0.5),
and troll **Almost** tells the truth 75% of times (P(Almost) = 0.75).

Let A = "Troll Honest answering" and B = "Troll tells the truth in all 5 questions asked".

 $$P(B) = P(B|Truth)P(Truth) + P(B|Half)P(Half) + P(B|Almost)P(Almost) $$
 $$= (1)^5\cdot\frac{1}{3} + (0.5)^2\cdot\frac{1}{3}+(0.75)^5\cdot\frac{1}{3}$$
 $$= 0.423$$
 
 $P(A) = \frac{1}{3}$
 
 $P(B|A) = 1$

Using Bayes' Rule: Probability that you are asking troll Honest given that it answers the truth to all 5 of your questions:

$$ P(A|B) = \frac{P(B|A)P(A)}{P(B)}$$
$$ = \frac{1\cdot\displaystyle\frac{1}{3}}{0.423}$$
$$ = 0.788$$

**b).** If you ask Troll A one more question, what is the probability that he will tell the truth again?

Solution:

Define: Troll **Honest** tells the truth 100% of times (P(Honest) = 1), troll **Half** tells the truth 50% of times (P(Half) = 0.5),
and troll **Almost** tells the truth 75% of times (P(Almost) = 0.75).

Let A1 = "Troll Honest answering", A2 = "Troll Half answering", A3 = "Troll Almost answering", 
and B = "Answer the truth to the previous 5 questions".

$$P(A1|B) = 0.788 \text{ (according to a))}$$
$$P(A2|B) = \frac{P(B|A2)P(A2)}{P(B)} = \frac{(\frac{1}{2})^5\cdot\frac{1}{3}}{0.423} = 0.0246$$
$$P(A3|B) = \frac{P(B|A3)P(A3)}{P(B)} = \frac{(\frac{3}{4})^5\cdot\frac{1}{3}}{0.423} = 0.187$$

P(That troll tells the truth to question 6 given that it answered the truth to the previous 5 questions)

$$= P(A1|B)P(Honest) + P(A2|B)P(Half) + P(A3|B)P(Almost)$$
$$= 0.788\cdot1 + 0.0246\cdot\frac{1}{2}+0.187\cdot\frac{3}{4} = 0.941$$

---


### Question 4
Fantasy Five is a lottery game you can play for $1. The way it works is, from the set 1,2,3,...,39, you
select a subset of 5 different values.\
The lottery commissioner also selects a set of 5 winning values uniformly at random.\
You win money based on how many of your values match with the winning values.

Here are the payouts:\
5 out of 5 pays $67000\
4 out of 5 pays $401\
3 out of 5 pays $15\
2 out of 5 pays $1\
1 out of 5 pays $0\
0 out of 5 pays $0

(a) What is the probability that you win something (at least 2 values in common with the winning values?)

* I can chooose 5 difeerent numbers from 1 to 39.
* Lottery also randomly picks 5 numbers from 1 to 39.
* I can win money depending on how many numbers match.

set the humber of matches K : 0,1,2,3,4,5.\
sets of winning numbers : $$\binom{39}{5}$$
$$P(K \geq 2) =  P(K=2) + P(K=3) + P(K=4)+P(K=5)\\
\rightarrow P(K=k) = \frac{\binom{5}{k}\binom{34}{5-k}}{\binom{39}{5}}$$
* $\binom{5}{k}$ : Choose 5 numbers match with winning numbers.
* $\binom{34}{5-k}$ : Choose the rest of the winning numbers from 34 of numbers you didn't pick.
* $\binom{39}{5}$ : Total possible numbers of winning numbers.\
When k=2, $\frac{{\binom{5}{2}}\binom{34}{3}}{\binom{39}{5}}\approx 0.1039$\
When k=3, $\frac{{\binom{5}{3}}\binom{34}{2}}{\binom{39}{5}}\approx 0.00974$\
When k=4, $\frac{{\binom{5}{4}}\binom{34}{1}}{\binom{39}{5}}\approx 0.000295$\
When k=5, $\frac{{\binom{5}{5}}\binom{34}{0}}{\binom{39}{5}}\approx 0.000001737$
$$\rightarrow P(K\geq2) = 0.1039 + 0.00974 + 0.000295 + 0.000001737 = 0.114 \approx 11.4\%$$


(b) What is the expected number of values your values have in common with the winning values?

* For each of your 5 chosen numbers, the chance it matches one of the 5 winning number is : P = $\frac{5}{39}$
* You have 5 numbers, so expected number math is : E[K] = 5 * $\frac{5}{39}$ = $\frac{25}{39} \approx 0.641$
* Your ticket shares approximately about 0.641 numbers in common with winning set on average.


(c)What is the expected profit you make from playing this game?

* Multiply each possible outcome by its probability.
$$E[Payout] = \sum_{k=0}^{5} Prize(k) * P(K = k)$$

When k=0 and k=1, E[payout] will be 0 since there's no prize for both of them.\
When k=2, E[payout] = 1 * 0.1039 = 0.1039\
When k=3, E[payout] = 15 * 0.00974 = 0.1461\
When k=4, E[payout] = 401 * 0.000295 = 0.1183\
When k=5. E[payout] = 67000 * 0.000001737 = 0.1164

$$\rightarrow \text{Total of E[Payout] = 0.1039 + 0.1461 + 0.1183 + 0.1164 = 0.4847}$$
$$\rightarrow \text{E[Profit] = Total of E[Payout] - 1,  since ticket cost 1 dollar}$$
$$\rightarrow \text{E[Profit] = 0.4847 - 1 = -0.5153}$$
