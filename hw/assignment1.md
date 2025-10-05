# Assignment 1

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu

Due: October 6 2025

---

Question 1. (a) Use regular induction to prove the following identity for all $n \ge 0$:
$$\sum_{k=0}^n k\cdot2^k=(n-1)\cdot2^{n+1}+2$$

<!--1.a should do on the following spaces--> 
$\text{Claim: } \displaystyle\sum_{k=0}^{n} k\cdot2^k = (n-1)\cdot2^{n+1} + 2 \text{ for all integers } n \ge 0$

$\text{Base case: } $ $n = 0$
                $$0\cdot2^0 = 0 = (0-1)\cdot2^{0+1} + 2$$
$\text{Induction Hypothesis:}$
    $$\text{Assume: }\sum_{k=0}^{m} k\cdot2^k = (m-1)\cdot2^{m+1} + 2 \text{ for some integer } m \ge 1$$
$\text{Induction Step:}$
$$\text{Start from } \sum_{k=0}^{m+1} k\cdot2^k = (m-1+1)\cdot2^{m+1+1}+2 $$
$$\sum_{k=0}^{m} k\cdot2^k + (m+1)2^{m+1} = m\cdot2^{m+2} + 2 $$
$$\lrArr \sum_{k=0}^{m} k\cdot2^k + (m+1)2^{m+1} = (m-1)\cdot2^{m+1} + 2^{m+1} + m\cdot2^{m+1} + 2$$
$\text{Since by the IH we know that}$ $$\sum_{k=0}^{m} k\cdot2^k = (m-1)\cdot2^{m+1} + 2$$
$\text{Then all that is left is to check if}$ 
        $$(m+1)\cdot2^{m+1} = 2^{m+1} + m\cdot2^{m+1}$$
    $$\hspace{67px}\lrArr (m+1)\cdot2^{m+1} = (m+1)\cdot2^{m+1} \hspace{120px}\textbf{(True)}$$

$\text{Conclusion:}$
$$\text{Since our claim holds for n = 0 and } \sum_{k=0}^{m} k\cdot2^k = (m-1)\cdot2^{m+1} + 2 $$ $$ \rightarrow \sum_{m=0}^{m+1} k\cdot2^k = (m-1+1)\cdot2^{m+1+1}+2 \text{ for } m\ge 0$$
$$\text{By induction, }\displaystyle\sum_{k=0}^{n} k\cdot2^k = (n-1)\cdot2^{n+1} + 2 \text{ for all integers } n \ge 0 $$

Question 1. (b) Use regular induction to prove the following identiy for all $n \ge 2$:
$$\sum_{k=1}^{n} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt n}$$

<!--1.2 should do on the following spaces-->
$\text{Claim: } \displaystyle\sum_{k=1}^{n} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt n} \text{ for all integers } n \ge 2$

$\text{Base case: } $ $n = 2$
                $$\sum_{k=1}^{2} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt 2}$$
                $$\lrArr1+\frac{1}{\sqrt2}>\sqrt2$$
                $$\lrArr 1>\sqrt{2} - \frac {1}{\sqrt{2}} = \frac{2-1}{\sqrt2}=\frac{1}{\sqrt2} $$
                $$\lrArr 1\gt\sqrt2-\frac{1}{\sqrt2}=\frac{2-1}{\sqrt2}=\frac{1}{\sqrt2}$$
                $$\lrArr\sqrt2\gt1\hspace{61px}\textbf{(True)}$$
$\text{Induction Hypothesis:}$
    $$\text{Assume: }\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt m}\text{ }\text{ for some integer } m \ge 2$$
$\text{Induction Step:}$

$\text{Start from } \displaystyle\sum_{k=1}^{m+1} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt{m+1}}$
$$\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right)+\frac{1}{\sqrt{m+1}} \gt{\sqrt{m+1}} $$

$\text{Since by the IH we know that}$ $$\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt m}$$
$\text{Which means:}$ 
        $$\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right)+\frac{1}{\sqrt{m+1}} \gt{\sqrt{m}}+\frac{1}{\sqrt{m+1}} $$
$\text{Then all that is left to check if}$
$${\sqrt{m}}+\frac{1}{\sqrt{m+1}}\gt\sqrt{m+1}$$
$$\lrArr\frac{\sqrt{m(m+1)}+1}{\sqrt{m+1}}\gt\sqrt{m+1}$$
$\text{Since}\sqrt{m(m+1)}+1\gt0\text{ and }\sqrt{m+1}>0\text{,}$
$$\sqrt{m(m+1)}+1\gt\text{m+1}$$
$$\lrArr\sqrt{m^2(1+\frac{1}{m})}\gt\text{m}$$
$$\lrArr m\sqrt{1+\frac{1}{m}}\gt m\cdot1$$
$\text{Because }m\ge2\gt0\text{ , then }\displaystyle\frac{1}{m}\gt0\text{, which means }\sqrt{1+\frac{1}{m}}\gt1$

$ \text{ So, }m\sqrt{1+\displaystyle\frac{1}{m}}\gt m\cdot1$

$\text{Therefore, }\displaystyle\sum_{k=1}^{m+1} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt{m+1}}$

$\text{Conclusion:}$

$\text{Since our claim holds for n = 2 and } \displaystyle\sum_{k=1}^{m} \left(\frac{1}{\sqrt k}\right) \gt{\sqrt m} $ $$ \rightarrow \displaystyle\sum_{k=1}^{m+1} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt {m+1}} \text{ for } m \ge 2 $$
$\text{By induction, }\displaystyle\sum_{k=1}^{n} \left(\frac{1}{\sqrt k} \right) \gt{\sqrt n} \text{ for all integers } n \ge 2$


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
