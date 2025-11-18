# Assignment 6

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: November 18 2025

---

### Question 1
**a).** Consider the recurrence relation:
$$P(0)=1$$
$$P(n)=3P(n-1)+3^n\text{ for }n \ge 1$$
Use the method of unraveling to find a closed-form expression for $P(n)$.

Solution:

$$\begin{align*}
    P(n)&=3P(n-1)+3^n \tag{1}\\
    P(n)&=3\Big(3P\big[(n-1)-1\bigl] + 3^{n-1}\Bigl) + 3^n \tag{2}\\
    &=3^2P(n-2)+3^{n-1}\cdot 3+3^n\\
    &=3^2P(n-2)+(2)3^n\\
    P(n)&=3^2\Big(3P\big[(n-2)-1\bigl]+3^{n-2}\Bigl)+(2)3^n\tag{3}\\
    &=3^3P(n-3)+(3)3^n\\
    \dots\\
    P(n)&=3^kP(n-k)+(k)3^n\tag{k}\\
    \dots\\
    P(n)&=3^nP(0)+(n)3^n\tag{n}\\
    &=3^n+(n)3^n\\
    P(n)&=3^n(n+1)
\end{align*}$$

**b).** Consider the recurrence relataion:
$$Q(1)=1,$$
$$Q(n)=Q(\frac{n}{3})+\log_3(n) \text{ for } n \ge 3$$
where n is power of 3.

Use the method of unraveling to find a closed-form expression for $Q(n)$. Hint: you can make a chage of variable and let $u = \log_3(n)$.

Solution:

Since $n=3^u$, let $u = \log_3(n)$. We know $Q(n) = Q(3^u)$.
$$Q(n)=Q(\frac{n}{3})+\log_3(n)$$
Therefore:

$$
\begin{align*}
    Q(3^u)&=Q(\frac{3^u}{3})+u\tag{Subsitiution}\\
    &=Q(3^{u-1})+u\\
    Q(3^u)&=\big[Q(3^{(u-1)-1})+(u-1)\bigl]+u\tag{2}\\
    &=Q(3^{u-2})+u+(u-1)\\
    Q(3^u)&=\big[Q(3^{(u-2)-1})+(u-2)\bigl]+u+(u-1)\tag{3}\\
    &=Q(3^{u-3})+u+(u-1)+(u-2)\\
    \dots\\
    Q(3^u)&=Q(3^{u-k})+u+(u-1)+\dots +(u-(k-1))\tag{k}\\
    \dots\\
    Q(3^u)&=Q(3^{u-u})+u+(u-1)+\dots +(u-(u-1))\tag{n}\\
    &=Q(1)+u+(u-1)+\dots +2+1\\
    &=Q(1)+\sum_{i=1}^u i\\
    Q(3^u)&=1+\frac{u(u+1)}{2}\\
    Q(n)&=1+\frac{\log_3(n)(\log_3(n)+1)}{2}\tag{Subsitiution}
\end{align*}
$$

---

### Question 2

Consider the recurrence $$C(n) = (4 - \frac{2}{n})C(n-1), C(0) = 1.$$

(a) Use induction to show that $$C(n) = \frac{(2n)!}{n!n!}$$

* Base Case n = 0 :
$$\text{Left hand side: } C(0) = 1\\
\text{Right hand side: } \frac{(2*0)!}{0!0!} = \frac{0!}{1*1} = 1\\
\rightarrow \text{Base case holds.}$$

* Inductive Step
$$\text{Assume for some } n - 1 \ge 0:$$
$$C(n-1) = \frac{(2n-2)!}{(n-1)!(n-1)!}$$
 and we have to show $$C(n) = \frac{(2n)!}{n!n!}$$
 * Use the recurrence: 
 $$C(n) = (4-\frac{2}{n})C(n-1)$$
 Simplify the coefficient :
 $$4-\frac{2}{n} = \frac{4n-2}{n} = \frac{2(2n-1)}{n}$$
 Then:
 $$C(n) = \frac{2(2n-1)}{n}*\frac{(2n-2)!}{(n-1)!(n-1)!} = \frac{(2n)(2n-1)(2n-2)!}{n(n-1)!(n-1)!}$$
 * Covert and simply
 $$(2n)! = (2n)(2n-1)(2n-2)!$$
 $$n!=n(n-1)!$$

When I substitute this into the equation, I get the answer :
$$C(n) = \frac{(2n)!}{n!n!}$$

(b) Use Stirling's approximation to show that $$C(n) \approx \frac{4^n}{\sqrt{\pi n}}$$
*Stirling's formula :
$$n!\approx\sqrt{2\pi n}(\frac{n}{e})^n$$

Apply this formula into the formula that we got from part(a) :
$$(2n)!\approx\sqrt{4\pi n}(\frac{2n}{e})^{2n}$$
$$n!\approx\sqrt{2\pi n}(\frac{n}{e})^n$$
Now we get,
$$C(n)\approx\frac{\sqrt{4\pi n}(\frac{2n}{e})^{2n}}{[\sqrt{2\pi n}(\frac{n}{e})^n]^2}$$

* Simplify Denomintor
$$C(n)\approx\frac{\sqrt{4\pi n}(\frac{2n}{e})^{2n}}{(2\pi n)(\frac{n}{e})^{2n}}$$

* Cancel exponential terms
$$\frac{(\frac{2n}{e})^{2n}}{(\frac{n}{e})^{2n}} = 2^{2n} = 4^n$$
So, now we get :
$$C(n)\approx 4^n*\frac{\sqrt{4\pi n}}{2\pi n}$$

*More simplify
$$C(n)\approx 4^n*\frac{2\sqrt{\pi n}}{2\pi n}$$
Cancel 2's :
$$ =4^n*\frac{\sqrt{\pi n}}{\pi n} = 4^n*\frac{1}{\sqrt{\pi n}}$$

Then we get final answer:
$$C(n)\approx\frac{4^n}{\sqrt{\pi n}}$$

---

### Question 3

**(a)** Let $R(n)$ be the number of strings over the alphabet $\{2, 3, 4, 6\}$ that sum to $n$ when all digits are added together.

For example, the string "2464" sums to 16.

(i) Derive a recurrence relation for $R(n)$ and justify why it holds.

(ii) Use the characteristic polynomial to determine the Big-Theta asymptotic growth of $R(n)$.

Solution:

Part (i): Recurrence Relation

Let $R(n)$ = number of strings over alphabet $\{2, 3, 4, 6\}$ that sum to $n$

Any string that sums to $n$ must end with one of the digits in $\{2, 3, 4, 6\}$.

- If the string ends with 2, the remaining digits must sum to $n-2$. There are $R(n-2)$ such strings.
- If the string ends with 3, the remaining digits must sum to $n-3$. There are $R(n-3)$ such strings.
- Similarly for 4 and 6: $R(n-4)$ and $R(n-6)$ respectively.

Thus, the recurrence relation is:

$$
R(n) = R(n-2) + R(n-3) + R(n-4) + R(n-6)
$$

Part (ii): Characteristic Polynomial

Guess that $R(n) = Ar^n$ for some constants $A$ and $r$.

Substituting into the recurrence:

$$
Ar^n = Ar^{n-2} + Ar^{n-3} + Ar^{n-4} + Ar^{n-6}
$$

Dividing both sides by $Ar^{n-6}$:

$$
r^6 = r^4 + r^3 + r^2 + 1
$$

Rearranging:

$$
r^6 - r^4 - r^3 - r^2 - 1 = 0
$$

Using an online polynomial solver, the roots are approximately:

- $r_1 \approx 1.5129$ (dominant root)
- $r_2 \approx -1.1787$
- $r_3 \approx -0.5 - 0.866i$
- $r_4 \approx -0.5 + 0.866i$
- $r_5 \approx 0.3329 - 0.671i$
- $r_6 \approx 0.3329 + 0.671i$

Therefore:

$$
R(n) = \Theta(r_1^n) = \Theta(1.5129^n)
$$

**(b)** Let $T(n)$ be the number of ternary (consist of the characters 0, 1, 2) strings of length $n$ that avoid the substring 01.

(i) Derive a recurrence relation for $T(n)$ and justify why it holds.
(Hint: use the expression $T_0(n)$ to signify the number of ternary strings of length $n$ that avoid 01 and start with 0.)

(ii) Use the characteristic polynomial to determine the Big-Theta asymptotic growth of $T(n)$.

Solution:

Part (i): Recurrence Relation

Let $T(n)$ = the number of ternary strings that avoid "01"

A ternary string of length $n$ avoiding "01" must start with one of the characters: 0, 1, or 2.

- If it starts with 1, then there are $T(n-1)$ ways to fill in the remaining $n-1$ entries with a 01-avoiding ternary string.
- If it starts with 2, similarly there are $T(n-1)$ ways to fill in the remaining $n-1$ entries with a 01-avoiding ternary string.
- If it starts with 0, then the next entry cannot be 1 (to avoid "01"). So there are two choices for what it could be: 0 or 2. Then there are $T(n-2)$ ways to fill in the remaining $n-2$ entries with a 01-avoiding ternary string.

Thus, the recurrence relation is:

$$
T(n) = 2T(n-1) + 2T(n-2)
$$

Part (ii): Characteristic Polynomial

Guess that $T(n) = Ar^n$ for some constants $A$ and $r$.

Substituting into the recurrence:

$$
Ar^n = 2Ar^{n-1} + 2Ar^{n-2}
$$

Dividing both sides by $Ar^{n-2}$:

$$
r^2 = 2r + 2
$$

Rearranging:

$$
r^2 - 2r - 2 = 0
$$

By the quadratic formula:

$$
r = \frac{-(-2) \pm \sqrt{(-2)^2 - 4(1)(-2)}}{2(1)}
$$

$$
r = \frac{2 \pm \sqrt{4 + 8}}{2} = \frac{2 \pm \sqrt{12}}{2}
$$

$$
r = \frac{2 \pm 2\sqrt{3}}{2} = 1 \pm \sqrt{3}
$$

The two roots are:

- $r_1 = 1 + \sqrt{3} \approx 2.732$ (dominant root)
- $r_2 = 1 - \sqrt{3} \approx -0.732$

Therefore:

$$
T(n) = \Theta(r_1^n) = \Theta((1+\sqrt{3})^n)
$$


Question 4: Consider the Sierpinski triangle fractal.

Let S(0) be a white equilateral triangle of area 1. To obtain S(n), subdivide each white triangle of S(n - 1) into 4 smaller congruent triangles and darken the central one.

a) Let E(n) denote the number of small white triangles remaining after n iterations. Formulate a recurrence relation for E(n).

**Solution**: Each white triangle from S(n-1) gets replaced by 3 white triangles and 1 black triangle when we advance to S(n). So E(n) = 3E(n - 1) with E(0) = 1.

b) Find a closed form of E(n)

**Solution**: Close form for E(n) is $E(n) = 3^n$

Base case: $E(0) = 1$ and $3^0 = 1$

Inductive Step: Let k be an arbitrary integer, k > 0. Assume that $E(k-1) = 3^{k-1}$. Then,
$$E(k) = 3E(k-1) = 3*3^ {k-1} = 3^k$$

c) Let A(n) be the total area of the white triangles of the nth Sierpinski triangle (with A(0) = 1).
Formulate a recurrence for A(n) and solve it for a closed form.

**Solution**: 

To get from S(n - 1) to S(n), each of the white triangle in E(n - 1) has its area divided into 4 equal triangles, 3 of which are white. In other words, from S(n - 1) to S(n), the area of a white triangle is reduced to only 3/4 of its area. Therefore, the total area of white triangle in S(n) is 3/4 of the total area of white triangle in S(n - 1).

$A(n) = \frac{3}{4}A(n-1)$, given that A(0) = 1

To get its closed form,

$A(n)= A(0)\cdot\displaystyle\prod_{k=1}^{n}\frac{3}{4}=A(n)= \displaystyle\prod_{k=1}^{n}\frac{3}{4} = \displaystyle{(\frac{3}{4})}^n$

d) As $n \rarr\infty$, what does A(n) approach?

**Solution**: 



$\lim\limits_{n\rarr\infty}A(n)=\lim\limits_{n\rarr\infty}{(\displaystyle\frac{3}{4})}^n= 0$ because $\displaystyle\frac{3}{4} < 1$
