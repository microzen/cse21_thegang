# Assignment 8

Contributors:
- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: December 2 2025

---

### Question 4
Recall that adjacency matrices of simple directed graphs are matrices consisting of 0’s and 1’s such
that there are no 1’s down the diagonal (no self loops, no parallel edges.)

For the questions below, suppose that A is the adjacency matrix of a simple directed graph G with n
vertices

**a)** Consider the graph and its adjacency matrix and compute the square of the adjacency matrix

Solution :

Using matrix multiplication to compute $A^2=A*A$

Example 1: entry(0,2) of $A^2$\
Row 0 of A : ( 0, 1, 1, 0, 0, 0)\
Coulumn 2 of A : ( 1, 1, 0, 0, 0, 0, 1)\
$(A^2)_{0,2} = (0 * 1) + (1 * 1) + (1 * 0) + (0 * 0) + (0 * 0) + (0 * 0) + (0 * 1) = 0 + 1 + 0 + 0 + 0 + 0 + 0 = 1$

Example 2: entry(0,4) of $A^2$\
Row 0 of A : (0, 1, 1, 0, 0, 0, 0)\
Column 4 of A : (0, 1, 1, 1, 0, 1, 0)\
$(A^2)_{0,4} = (0 * 0) + (1 * 1) + (1 * 1) + (0 * 1) + (0 * 0) + (0 * 1) + (0 * 0) = 0 + 1 + 1 + 0 + 0 + 0 + 0 = 2$

I would repeat this for every pair (i,j). Doing all of them with software then gives :

$$
A^2 = \begin{bmatrix}
{0} & {0} & {1} & {0} & {2} & {0} & {0}\\
{1} & {0} & {0} & {0} & {1} & {0} & {0}\\
{1} & {0} & {0} & {0} & {0} & {0} & {0}\\
{1} & {1} & {2} & {0} & {0} & {1} & {0}\\
{0} & {1} & {1} & {0} & {0} & {0} & {0}\\
{2} & {0} & {0} & {0} & {1} & {0} & {1}\\
{0} & {0} & {0} & {1} & {2} & {0} & {0}\\
\end{bmatrix}
$$

**b)** Consider an adjacency matrix A for an arbitrary simple directed graph let $a_{i,j}$ be the (i,j) entry of A. Let $x_{i,j}$ entry of $A^2$.

Give an argument that $x_{i,j}$ is the number of length 2 walks from i to j in the original graph A.

Solution :

Let A be the adjacency matrix of a directed graph.
* $a_{ik}$ = 1 , iff there is an edge $ i \rightarrow k$.
* $a_{ik}$ = 0 , otherwise.

By definition of matrix multiplication, fix a vertex k.
* If there is a path $i \rightarrow k \rightarrow j$, then $a_{ik} = 1$ and $a_{kj} = 1$, so $a_{ik}a_{kj} = 1$.\
This corresponds to one length 2 walk from $i$ to $j$ going through $k$.
* If that path does not exist, then at least one of $a_{ik},a_{kj}$ is 0, so $a_{ik}a_{kj} = 0$

Therefore, the sum counts how many $k$'s give a valid walk $i\rightarrow k\rightarrow j$. So $x_{ij}$ is exactly the number of walks of length 2 from vertex $i$ to vertex $j$.

**c)** Explain why if G is a DAG then there exists some $t\ge2$ such that $A^t$ is the zero matrix ( matrix of all zeros. )

Explaination :

Any directed walk of length $t$ uses $t$ edges and therefore visits $t+1$ vertices.

If $t\ge n$, then $t+1 \ge n+1$, so a walk of length $t$ would visit at least $n+1$ vertices, but the graph has only $n$ vertices.

By the pigeonhole principle, some vertex must be repeated.

The segment of the walk between the first and second visit to that vertex is a directed cycle.

But, $G$ is a DAG, so it has no directed cycles, so no directed walk of length $t\ge n$ can exist in $G$.

Since for this problem I can assume that the $(i,j)$ entry of $A^t$ equals the number of length $t$ walks from $i$ to $j$.

Also, since there are no such walks when $t\ge n$, every entry of $A^t$ is 0 for $t\ge n$.

In particular, choosing $t=n\ge 2$ I get $A^t = A^n = 0$, the zero matrix.