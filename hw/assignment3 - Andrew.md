2b)  Suppose you are leaving out a bowl of 10 candies to trick-or-treaters. You have an unlimited
supply of 6 different candy bars: Snickers, Milky way, 3 Musketeers, Almond Joy, Twix, Kit Kat.
You don’t really know what candies to give out so you use a random sampling process to select
the candies:
You roll a 6-sided die ten times in a row. If you roll a 1, you put a Snickers in the bowl, if you
roll a 2, you put a Milky Way in the bowl, if you roll a 3, you put a 3 Musketeers in the bowl, if
you roll a 4, you put an Almond Joy in the bowl, if you roll a 5, you put a Twix in the bowl and
if you roll a 6, you put a Kit Kat in the bowl.
i) Explain why this is not a uniform random sampling

Definition of uniform sampling: Every outcome has the same probability.

Assume the trick-or-treaters getting candies from a bowl of 10 candies is a uniform random sampling. That means each type of candy has the same probability of being taken by the trick-or-treaters.

We have 10 candies in that bowl using 6 types of candies. 10 is not divisible by 6, which means at least one type of candy has more candies in the bowl than another type of candy. We call them candy A and B, respectively.

Let the number of candies A is x, and the number of candies B is y. 

The difference between x and y is k ($k \in N, k \neq 0$).

$$P(B) = \frac{y}{10}\text{ , while }P(A) = \frac{x}{10} = \frac{y + k}{10}$$

We clearly see that $P(A) \neq P(B)$, which contrast with the initial theory. Therefore, this is not a uniform random sampling.

3. You are on a quest and you arrive at 3 trolls (Troll A, Troll B, Troll C)
each standing in front of a door (door A, door B, door C). You know that one troll tells the truth all
the time another troll tells the truth with a probability of 1/2 and lies with a probability of 1/2 and
another troll tells the truth with a probability of 3/4 and lies with a probability of 1/4.
You don’t know which troll is which. The door behind the truthful troll goes to the next quest and
the doors behind the other two trolls send you back to the beginning.
You wish to determine which troll is telling the truth and you get to ask 5 questions to any of the
trolls.
You decide to ask 5 obvious questions to Troll A and learn that Troll A told the truth all 5 times.
(a) What is the probability that Troll A is the truthful troll? (Troll A tells the truth all the time.)

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

b) If you ask Troll A one more question, what is the probability that he will tell the truth again?

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


 
