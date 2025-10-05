# Assignment 1

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- [First and Last Name], [Email]

Due: October 6 2025

---

Question 1. (a) Use regular induction to prove the following identity for all $n \ge 0$:
$$\sum_{k=0}^n k2^k=(n-1)2^{n+1}+2$$

<!--1.a should do on the following spaces-->

Question 1. (b) Use regular induction to prove the following identiy for all $n \ge 2$:
$$\sum_{k=1}^{n} \left({1/\sqrt k }\right) \gt{\sqrt n}$$

<!--1.2 should do on the following spaces-->


---
Question2: A password is a string over the alphabet of 72 characters consisting of the 26 uppercase letters, the 26 lowercase letters, the 10 digits, and the 10 special characters: {!,@,#,$,%,&,*,?,+,=,-}

(a) How many 8-character passwords have at least 2 letters (they can each be uppercase or lower case)?

$$\text{Total = Least 2 Letter + Exactly One Letter + Zero Letter}$$
$$72^8= \text{Least 2 Latter} + (52)(20)^7+(20)^8$$
$$\text{Least 2 Latter} = 72^8 - (52)(20)^7 - (20)^8$$

(b) How many 8-character passwords avoids the word COUNT all in uppercase?

$$72^8-(3)(72)^3$$

(c) How many 8-character passwords consist of 4 different characters with 2 copies of one, 2 copies of another, 3 copies of another, and a sigle copy of the last?



(d) How many 8-character passwords

(e) How many 8-character passwords

---

QUESTION 3
For each expression, describe a set of objects that is counted by the expression and
include your reasoning.

(a) $$ 26 * 8 * 10^7 $$
 Answer : 8 character string with excatly one letter and 7 digits.
 
 Reason : choosing letter out of 26 ways, choosing position out of 8, then 7 positions reamins with any digit.

(b) $$ 10^3(26+10)^5 \binom{8}{3} $$
Answer : 8 character strings together with 3 digit only positions and 5 of any letter or digits.

Reason : choosing the 3 on digit only position out of 8 and put any digits in those positions and fill remaining position with any letters or digits.

(c) $$ (26 + 10)^8 - 26^8 $$
Answer : 8 character strings that have at least one digit.

Reason : all letter or digit strings of length 8 and take out the strings made of letters only.

(d) $$ 26^8 + 10^8 + 10^4 * 26^4 $$
Answer : 8 character strings that all letters or all digits or have 4 digits and 4 letters positions.

Reason : add all the counts