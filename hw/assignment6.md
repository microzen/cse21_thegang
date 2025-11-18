# Assignment 6

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: November 18 2025


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