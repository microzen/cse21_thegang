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