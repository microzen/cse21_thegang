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