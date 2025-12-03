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
