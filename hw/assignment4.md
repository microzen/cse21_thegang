# Assignment 4

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: October 27 2025


---

### Question 4

For each algorithm, compute the exact number of times the algorithm prints in terms of n
where n ¥ 3. (We use the convention that if there is a for loop such that the starting value is greater
than the ending value, then that loop does not run and for loops include both endpoints.)

(a) $$\text{for } i = 1 \text{ to } n \\
\quad \quad\quad \text{for } j = i \text{ to } i + 2 \\
\quad\quad \quad \text{print } (i, j)$$

- Values are i, i+1, i+2. for each fixed i, the inner loop prints 3 times. i goes from 1 to n, so there are n choices of 1. Each choice contributes 3 prints
*Answer : 3n

(b) $$\text{for }i = 0 \text{ to }n -1\\
\quad\quad\text{for }j = 1 \text{ to } 2^i\\
\quad\quad\quad\text{print }(i,j)$$

- j runs from 1 to $2^i$, $2^i$ prints for that i.
$$\rightarrow 1+2+4+ ... + 2^{n-1} $$
Sum over all i then total prints will be $\sum_{i=0}^{n-1} 2^i.$
* Answer: $\sum_{i=0}^{n-1} 2^i$

(c) $$\text{for } i = 3 \text{ to } n\\
\quad\quad\quad\text{for } j = 2 \text{ to } i-1\\
\quad\quad\quad\quad\text{for } k = 1 \text{ to } j-1\\
\quad\quad\quad\quad\text{print } (i,j,k)$$

- Exapnding the loops mathematically then : $\sum_{i=3}^{n} \sum_{j=2}^{i-1} \sum_{k=1}^{j-1} 1$
$$\rightarrow \sum_{k=1}^{j-1} 1 = j-1\\
\rightarrow \sum_{i=3}^{n} \sum_{j=2}^{i-1}(j-1)\\
\rightarrow \sum_{j=2}^{i-1}(j-1) = \sum_{j=1}^{i-2}j\\
\rightarrow \sum_{i=3}^{n} \sum_{j=1}^{i-2}j\\
\text{equation 1: } \sum_{i=1}^{n}i = \frac{n(n+1)}{2} \\
\text { by using this equtions, we can make } \\
\sum_{i=3}^{n}\frac{(i-2)(i-1)}{2} = \sum_{i=1}^{n}\frac{(i-2)(i-1)}{2}-\frac{(2-2)(2-1)}{2}-\frac{(1-2)(1-1)}{2}\\
\text{since i=1 and i=2 will be cancled out, we'll get}\\
\sum_{i=1}^{n}\frac{(i-2)(i-1)}{2} \text { and we can expand the equation.}\\
\rightarrow \frac{1}{2}\sum_{i=1}^{n}(i^2-3i+2) = \frac{1}{2}(\sum_{i=1}^{n}i^2-3\sum_{i=1}^{n}i+2\sum_{i=1}^{n}1)\\
\text{equation 2: } \sum_{i=1}^{n}i^2 = \frac{n(n+1)(2n+1)}{6} \\
\text { by using this equtions, we can make: } \frac{1}{2}(\frac{n(n+1)(2n+1)}{6}-3(\frac{n(n+1)}{2})+2n)\\
= \frac{1}{12}(n(n+1)(2n+1)-9n(n+1)+12n) = \frac{n}{12}((n+1)(2n+1)-9(n+1)+12)\\
= \frac{n}{12}(2n^2+n+2n+1-9n-9+12) = \frac{n}{12}(2n^2-6n+4) = \frac{n}{6}(n^2-3n+2)\\
\text{now, we did all algebra and simplify and take an answer}\\
\text{ Answer : }\frac{n(n-1)(n-2)}{6}$$
