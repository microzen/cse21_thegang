# Assignment 8

Contributors:

- Yezhi Wu, yew020@ucsd.edu
- Andrew Le, aal034@ucsd.edu
- Theo Lee, thl030@ucsd.edu
- Woosik Kim, wok017@ucsd.edu

Due: December 2 2025

---

### Question 1

In a round robin tournament with n players, each player plays each other player. In each
game there is always a winner and a loser (no ties.) We can draw a graph to model a round robin
tournament that has a vertex for each player and a directed edge from x to y if player x won the game
against y.

For example, if there were 4 players 1, 2, 3, 4, 5, and the results of the games are:

1 wins against 2

1 loses against 3

1 wins against 4

1 wins against 5

2 loses against 3

2 loses against 4

2 wins against 5

3 loses against 4

3 loses against 5

4 wins against 5

Notice that this graph has a hamiltonian path: (3, 1, 4, 2, 5).
Prove that for any integer $n \ge 1$, any tournament graph on n vertices has a hamiltonian path (a path
that goes through each vertex exactly once.)

(Fill in the blanks of the proof by induction:)

**Solution:**

**Base Case:** if the tournament has 1 player then the graph with only one vertex has a trivial hamiltonian path.

**Inductive Step:** Let n be an arbitrary integer such that n > 1.

Assume that any tournament with n − 1 players, the corresponding graph has a hamiltonian path.

Consider an arbitrary tournament T with n players {1, . . . , n}

Then if you consider the tournament T ′ involving only {1, . . . , n − 1}, then by the inductive
hypothesis, there is a hamiltonian path $(a_1, . . . , a_{n−1})$ in the corresponding graph.

(Want to show there is a hamiltonian path in the tournament T)

**Case 1:** player n wins against player a1. Then T has the hamiltonian path **[ $(n,a_1,...,a_{n-1})$ ]**

**Case 2:** player $a_{n-1}$ wins against player n. Then T has the hamiltonian path: **[ $(a_1,...,a_{n-1},n)$ ]**

**Case 3:** player n loses against player $a_1$ and player n wins against player $a_{n-1}$. Then T has the hamilton path **[ $(a_1,...,a_{k-1},n,a_{k},...,a_{n-1})$ ]**

(Hint: Consider the sequence of wins and losses of player n against $a_1,a_2,...,a_{n-1}$ and notice that the sequence starts with a loss and ends with a win.)

---

### Question 2

Dominos is a game played with collection of tiles that have a number of “pips” on each side of the domino. For this problem, we will consider “double-twelve” dominos meaning that the number of pips can range anywhere from 0 to 12 on each side.

A “train” of dominos is a sequence of dominos such that two dominos next to each other “connect” with the same number of pips. You are given a collection of n dominos from the set of double-twelve dominos. You wish to determine if it is possible to make a train that uses all n dominos (each exactly once.)

For example: the collection: { (3, 5), (4, 5), (3, 3), (5, 11), (10, 5), (10, 4) } can be arranged in a train that includes all dominos:(11, 5), (5, 10), (10, 4), (4, 5), (5, 3), (3, 3)

On the other hand, the collection: { (3, 5), (4, 5), (3, 3), (5, 11), (10, 5) } cannot be arranged in a train that includes all dominos.

**a)**. Model this problem as a graph problem in such a way that, given the collection of n dominos, build a graph G such that G has a Eulerian path if and only if the collection of n dominos can be arranged in a train that includes all dominos. (An Eulerian path is a path that goes through each edge exactly once.) (Your answer should be a description of a graph for a general collection of dominos. You must have a clear description of the vertices and a clear rule about when two vertices are connected by an edge and whether or not the edge is directed or undirected.)

**Solution:** Since an Eulerian part is defined as a trail in a finite graph which visist every edge exacly once, the domaines themselfe must be the edges. 

For vertices, $V=\{0,1,2,3,4,\dots ,12\}$ which is the number of pips on the faces of the dominoes.

For edges, create an undirected edge between two vertices $u$ and $v$ for each dominoes $(u,v)$ in the collection. The other situation could be a double $(u,u)$, which was crated by a self-loop on vertex.

The reason of this graphs works on Eulerian is :

Suppose that the graph has an Eulerian path from $(v_1,\dots ,v_n)$. Then, for each edges travers by using the specific domino from the collection exactly onece. Since the edges in the path are connected by both normal vertices and double vertices, the corresponding dominos share the common number of pips at $v_i$ and $v_{i+1}$. Therefore, the sequence $(v_1,\dots ,v_n)$ of edges in the Eulerian path corresponds to a valid train that uses all dominos.

**b)**. If there are n dominos, how many vertices and edges does your graph have (worst-case using Big-O notation)

**Solution**: 

In the worst case of vertices, the number of vertices is bounded by the number of pip valuse, which is the set $\{0,1,\dots ,12\}$. Therefore, there are $13$ vertices. $|V| \in O(1)$

In the worst case of edges, since every domino must be connected by exactly one edge, the number of edges is exactly $n$. Therefore, $|E| \in O(n)$

**c)**. Draw the graph for the input: {(6, 7), (10, 1), (3, 9), (12, 6), (9, 7), (7, 7), (5, 12), (7, 12), (3, 5), (3, 10), (1, 7), (6, 1)} (Try your best to draw your graph as a planar graph meaning that none of the edges cross.)

![eg](./Eulerian_graph.png)

**d)**. Identify a Eulerian path in the graph you built for part c and use that to construct a valid train.

- Vertex 1 -> (6,7,10): **Degree 3, Odd**
- Vertex 3 -> (5,9,10): **Degree 3, Odd** 
- Vertex 5 -> (3,12): Degree 2, Even
- Vertex 6 -> (1,7,12): **Degree 3, Odd** 
- Vertex 7 -> (1,6,9,12) + (itself): Degree 6, Even
- Vertex 9 -> (3,7): Degree 2, Even 
- Vertex 10 -> (1,3): Degree 2, Even 
- Vertex 12 -> (5,6,7): **Degree 3, Odd** 

Since it is more than 2 even degrees, there is no Eulerian path exists.

Valid train: (12,6)(6,7)(7,12)(12,5)(5,3)(3,9)(9,7)(7,7)(7,1)(1,10)(10,3)

By removing the (6,1) which will case vertex 1 and 6 to be even degress. Now, it is a valid Eulerian path.

---

### Question 3

A labeled 0-rooted tree with $n$ vertices is a rooted tree with each vertex labeled a different integer from 0 to n - 1 such that 0 is the root.

Consider the following encoding scheme for labeled 0-rooted trees with 8 vertices that uses 21 bits:

1. First convert the tree into a 7-tuple where the 1st entry is the parent of vertex 1, the 2nd entry is the parent of vertex 2, and so on.
2. Then convert the 7-tuple into a 21-bit string by converting each entry of the 7-tuple into a 3-bit integer in binary.

For Example: For the following tree:

The 7-tuple would be: (7, 7, 0, 1, 7, 4, 0) and the corresponding encoding: 111 111 000 001 111 100 000.

Encoding Table

| Decimal | Binary |
| :-----: | :----: |
|    0    |  000  |
|    1    |  001  |
|    2    |  010  |
|    3    |  011  |
|    4    |  100  |
|    5    |  101  |
|    6    |  110  |
|    7    |  111  |

**(a)** Use the encoding on the following trees: (no justification necessary)

Solution:

**(i)** Tree 1:

7-tuple: (0, 5, 6, 5, 1, 0, 0)

$$
000\ 101\ 110\ 101\ 001\ 000\ 000
$$

**(ii)** Tree 2:

7-tuple: (0, 0, 1, 1, 2, 2, 3)

$$
000\ 000\ 001\ 001\ 010\ 010\ 011
$$

**(iii)** Tree 3:

7-tuple: (0, 0, 0, 0, 0, 0, 0)

$$
000\ 000\ 000\ 000\ 000\ 000\ 000
$$

**(b)** Draw the labeled tree that is encoded by the string: (no justification necessary)

$$
101\ 100\ 000\ 111\ 011\ 101\ 000
$$

Solution:

7-tuple:

$$
(5, 4, 0, 7, 3, 5, 0)
$$

Parent relationships:

| Vertex | Parent |
| :----: | :----: |
|   1   |   5   |
|   2   |   4   |
|   3   |   0   |
|   4   |   7   |
|   5   |   3   |
|   6   |   5   |
|   7   |   0   |

Tree:

```
       0
      / \
     3   7
     |   |
     5   4
    / \   \
   1   6   2
```

**(c)** Is this encoding a bijection from the set of labeled 0-rooted trees with 8 vertices to the set of 21-bit strings?

Solution:

No, this encoding is not a bijection.

The encoding is injective (one-to-one) but not surjective (onto).

Counterexample:

Consider the 21-bit string:

$$
001\ 001\ 001\ 001\ 001\ 001\ 001
$$

This corresponds to the 7-tuple (1, 1, 1, 1, 1, 1, 1), which means vertex 1's parent is vertex 1 itself.

A vertex cannot be its own parent, so this is not a valid tree.

Since there exists a 21-bit string that doesn't correspond to a valid labeled 0-rooted tree, the encoding is not surjective, therefore not a bijection.

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
