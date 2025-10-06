# Assignment 1

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu

Due: October 6 2025

---

### Question 1. (a)
Use regular induction to prove the following identity for all $n \ge 0$:
$$\sum_{k=0}^n k\cdot2^k=(n-1)\cdot2^{n+1}+2$$

<!--1.a should do on the following spaces--> 
$\text{Claim: } \displaystyle\sum_{k=0}^{n} k\cdot2^k = (n-1)\cdot2^{n+1} + 2 \text{ for all integers } n \ge 0$

$\text{Base case: } n = 0$

$$0\cdot2^0 = 0 = (0-1)\cdot2^{0+1} + 2$$

$\text{Induction Hypothesis:}$

$$\text{Assume: }\sum_{k=0}^{m} k\cdot2^k = (m-1)\cdot2^{m+1} + 2 \text{ for some integer } m \ge 1$$

$\text{Induction Step:}$

$$\text{Start from } \sum_{k=0}^{m+1} k\cdot2^k = (m-1+1)\cdot2^{m+1+1}+2 $$

$$\sum_{k=0}^{m} k\cdot2^k + (m+1)2^{m+1} = m\cdot2^{m+2} + 2 $$

$$\leftrightarrow \sum_{k=0}^{m} k\cdot2^k + (m+1)2^{m+1} = (m-1)\cdot2^{m+1} + 2^{m+1} + m\cdot2^{m+1} + 2$$

$\text{Since by the IH we know that}$

$$\sum_{k=0}^{m} k\cdot2^k = (m-1)\cdot2^{m+1} + 2$$

$\text{Then all that is left is to check if}$ 

$$(m+1)\cdot2^{m+1} = 2^{m+1} + m\cdot2^{m+1}\leftrightarrow (m+1)\cdot2^{m+1} = (m+1)\cdot2^{m+1}\ \textbf{(True)}$$

$\text{Conclusion:}$

$$\text{Since our claim holds for n = 0 and } \sum_{k=0}^{m} k\cdot2^k = (m-1)\cdot2^{m+1} + 2$$

$$ \rightarrow \sum_{m=0}^{m+1} k\cdot2^k = (m-1+1)\cdot2^{m+1+1}+2 \text{ for } m\ge 0$$

$$\text{By induction, }\displaystyle\sum_{k=0}^{n} k\cdot2^k = (n-1)\cdot2^{n+1} + 2 \text{ for all integers } n \ge 0$$

### Question 1. (b)
Use regular induction to prove the following identiy for all $n \ge 2$:
$$\sum_{k=1}^{n} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt n}$$

<!--1.2 should do on the following spaces-->
$\text{Claim: } \displaystyle\sum_{k=1}^{n} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt n} \text{ for all integers } n \ge 2$

$\text{Base case: } n = 2$

$$\sum_{k=1}^{2} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt 2}$$

$$\leftrightarrow1+\frac{1}{\sqrt2}>\sqrt2$$

$$\leftrightarrow 1>\sqrt{2} - \frac {1}{\sqrt{2}} = \frac{2-1}{\sqrt2}=\frac{1}{\sqrt2} $$

$$\leftrightarrow 1\gt\sqrt2-\frac{1}{\sqrt2}=\frac{2-1}{\sqrt2}=\frac{1}{\sqrt2}$$

$$\leftrightarrow\sqrt2\gt1\hspace{61px}\textbf{(True)}$$

$\text{Induction Hypothesis:}$

$$\text{Assume: }\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt m}\text{ }\text{ for some integer } m \ge 2$$

$\text{Induction Step:}$

$\text{Start from } \displaystyle\sum_{k=1}^{m+1} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt{m+1}}$

$$\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right)+\frac{1}{\sqrt{m+1}} \gt{\sqrt{m+1}} $$

$\text{Since by the IH we know that}$ 

$$\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt m}$$

$\text{Which means:}$ 

$$\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right)+\frac{1}{\sqrt{m+1}} \gt{\sqrt{m}}+\frac{1}{\sqrt{m+1}} $$

$\text{Then all that is left to check if}$

$${\sqrt{m}}+\frac{1}{\sqrt{m+1}}\gt\sqrt{m+1}$$

$$\leftrightarrow\frac{\sqrt{m(m+1)}+1}{\sqrt{m+1}}\gt\sqrt{m+1}$$

$\text{Since}\sqrt{m(m+1)}+1\gt0\text{ and }\sqrt{m+1}>0\text{,}$

$$\sqrt{m(m+1)}+1\gt\text{m+1}$$

$$\leftrightarrow\sqrt{m^2(1+\frac{1}{m})}\gt\text{m}$$

$$\leftrightarrow m\sqrt{1+\frac{1}{m}}\gt m\cdot1$$

$\text{Because }m\ge2\gt0\text{ , then }\displaystyle\frac{1}{m}\gt0\text{, which means }\sqrt{1+\frac{1}{m}}\gt1$

$\text{ So, }m\sqrt{1+\displaystyle\frac{1}{m}}\gt m\cdot1$

$\text{Therefore, }\displaystyle\sum_{k=1}^{m+1} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt{m+1}}$

$\text{Conclusion:}$

$\text{Since our claim holds for n = 2 and } \displaystyle\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt m}$ 

$$ \rightarrow \displaystyle\sum_{k=1}^{m+1} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt {m+1}} \text{ for } m \ge 2 $$

$\text{By induction, }\displaystyle\sum_{k=1}^{n} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt n} \text{ for all integers } n \ge 2$


---
### Question 2: 
A password is a string over the alphabet of 72 characters consisting of the 26 uppercase letters, the 26 lowercase letters, the 10 digits, and the 10 special characters: {!,@,#,$,%,&,*,?,+,=,-} (*2 points for correct expression and 2 points for justiﬁcation*)

(a) How many 8-character passwords have at least 2 letters (they can each be uppercase or lower case)?

$$\text{Total = Least 2 Letter + Exactly One Letter + Zero Letter}$$
$$72^8= \text{Least 2 Latter} + (52)(20)^7+(20)^8$$
$$\text{Least 2 Latter} = 72^8 - (52)(20)^7 - (20)^8$$
$$72^8 - (52)(20)^7 - (20)^8$$

(b) How many 8-character passwords avoids the word COUNT all in uppercase?

Total is $72^8$, now, there are four different cases with the word **COUNT**: COUNTxxx, xCOUNTxx, xxCOUNTx, and xxxCOUNT.

So the answer is: $\text{Total } - \text{ four cases }\times \text{ 72 latters in 3 speace}$

$$72^8-(4)(72)^3$$

(c) How many 8-character passwords consist of 4 different characters with 2 copies of one, 2 copies of another, 3 copies of another, and a sigle copy of the last?

First, choose 4 different characters from all characters:

$$\dbinom{72}{4}$$

Then, choose 1 characters from the picked 4, and make 2 copies for two speaces of 8-character:

$$\dbinom{4}{1}\dbinom{8}{2}$$

choose 1 characters from the remain 3, and make 2 copies for two speaces of 8-character:

$$\dbinom{3}{1}\dbinom{6}{2}$$

choose 1 characters from the remain 2, and make 3 copies for three speaces of 8-character:

$$\dbinom{2}{1}\dbinom{4}{3}$$

choose 1 characters from the last one, and sigle copy for the last speaces of 8-character:

$$\dbinom{1}{1}\dbinom{1}{1}$$

Then, the answer is:

$$\dbinom{72}{4}\dbinom{4}{1}\dbinom{8}{2}\dbinom{3}{1}\dbinom{6}{2}\dbinom{2}{1}\dbinom{4}{3}\dbinom{1}{1}\dbinom{1}{1}$$


(d) How many 8-character passwords have exactly 3 different special characters?

We need exactly 3 different special characters. Therefore, take 3 different from 10 special characters. Also, 5 without special characters.

$$\dbinom{10}{3}\dbinom{8}{3}+(72-10)^7$$

So, the answer is:

$$\dbinom{10}{3}\dbinom{8}{3}+(62)^7$$


(e) How many 8-character passwords consist of 8 different letters (they cach can be uppercase or lowercase, but they must be different letters. For example, you cannot have AaBbCcDd but it is fine to have ZpxTaHwy.)?

First, we pick 1 from 52, then pick 1 from 50, then pick 1 from 48 ..... pick 1 from 38.

Therefor, we got

$$(52)\times(50)\times(48)\times\dots\times(38)$$
$$=2(26)(25)(24)(23)(22)(21)(20)(19)$$
$$=2\times\frac{26!}{18!}$$

---
Question4: (please include justification)

(a) (4 points)\
How many different ways are there to arrange the letters in the string UNITEDSTATES?

$$\frac{12!}{3!\,2!\,2!}$$

(b) (4 points)\
How many different ways are there to color the 8 \emph{vertices} of a cube with 8 different colors?

$$\frac{8!}{24}$$

(c) (4 points)\
How many different ways are there to make a necklace with 8 different colored beads (two necklaces are the same if you can manipulate one to look like the other.)

$$\frac{8!}{16}$$
