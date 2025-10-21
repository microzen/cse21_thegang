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

Explaination: North player has 7 chances to have his tiles in the opening hand. Since the probability to have double-six is $\frac{1}{28}$, thus, the probability of having double-six in the opening is $\frac{1}{28}+\frac{1}{28}+\dots+\frac{1}{28}$ seven times.

$$\frac{7}{28} = \frac{1}{4}$$


**b).** What is the probability that North has at least one double in their opening hand?

Explaination: Base on the formual $P(E)=\frac{|E|}{|S|}$, let's set the $E$ as the outcome of no double in opening hand. Set $S$ as the outcome of having tiles.

1. For E, chose 7 from the other $28 - 7$, which means the 7 pairs out of the total. Thus, $E = \dbinom{21}{7}$
2. For S, chose 7 from 28, thus, $S= \dbinom{27}{7}$
3. Now, the probability of least one double in opening hand is (1 - the probability of no double).

$$P(E) = 1 - \frac{\text{the outcome of no double}}{\text{the outcome of 7 chance having tiles}}$$

$$P(E)=1 - \frac{\dbinom{21}{7}}{\dbinom{28}{7}}$$


**c).** What is the probability that North and South together hold all 7 tiles containing the value 6?

Explaination: Total tiles North and South have is 14, so let set space as the outcome of having 14 tiles from 28.

Now, the 7 tiles containing the value 6 is inclueded in the space. Let's set E as the is the remaning 7 tiles from 21.

$$P(E)=\frac{\dbinom{7}{7}\dbinom{21}{7}}{\dbinom{28}{14}}$$


**d).** Suppose that you are player North and you hold 4 of the 7 tiles with the number 6: (6,6),(6,4),(6,2),(6,1) (along with 3 other tiles without 6). What is the probability that your partner (player South) holds the remaining 3 tiles with the number 6: (6,5),(6,3),(6,0)?

Solutation: Since North already recived 7 tiles, there are 21 tiles left. South drows 7 tiles form these 21. Among then, 3 must be the remaining 6 tiles, 4 could be random.

$$P(E) = \frac{\dbinom{3}{3}\dbinom{18}{4}}{\dbinom{21}{7}}$$


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
$$\rightarrow \text{E[Profit] = Total of E[Payout] - 1,  since ticket cost \$1}$$
$$\rightarrow \text{E[Profit] = 0.4847 - 1 = -0.5153}$$