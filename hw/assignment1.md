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
$$72^8 - (52)(20)^7 - (20)^8$$

(b) How many 8-character passwords avoids the word COUNT all in uppercase?

$$72^8-(3)(72)^3$$

(c) How many 8-character passwords consist of 4 different characters with 2 copies of one, 2 copies of another, 3 copies of another, and a sigle copy of the last?


$$\dbinom{72}{2}\dbinom{4}{1}\dbinom{8}{2}\dbinom{3}{1}\dbinom{6}{2}\dbinom{2}{1}\dbinom{4}{3}\dbinom{1}{1}\dbinom{1}{1}$$


(d) How many 8-character passwords have exactly 3 different special characters?

$$(72)^8-(20)^3$$


(e) How many 8-character passwords consist of 8 different letters (they cach can be uppercase or lowercase, but they must be different letters. For example, you cannot have AaBbCcDd but it is fine to have ZpxTaHwy.)?

$$\dbinom{52}{1} \dbinom{8}{1} \dbinom{50}{1} \dbinom{7}{1} \dbinom{48}{1} \dbinom{6}{1} \dbinom{46}{1} \dbinom{5}{1} \dbinom{44}{1} \dbinom{4}{1} \dbinom{42}{1} \dbinom{3}{1} \dbinom{40}{1} \dbinom{2}{1} \dbinom{38}{1} \dbinom{1}{1}$$

$$(8!)(\frac{52!!}{36!!})$$

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
