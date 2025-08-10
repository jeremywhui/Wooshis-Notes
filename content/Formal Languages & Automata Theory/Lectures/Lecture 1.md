# 1/22/25 - Cantor's Diagonalization Argument
- Theoretical foundations of CS
- Follow up to CS 205 and CS 344
- Contemplation along with mathematical proofs
- Convey ideas

There are an infinite number of primes
- Suppose there are a finite number of primes
- So there is a largest prime $p_n$
- Then $p_1 \cdot p_2 \cdot \ldots \cdot p_{n} + 1$ is prime, but not in the list

Understanding the limitations of computations
- To get a realistic view of CS
- Truth behind what is done

Grades:

| HW  | Due   | Exam  |
| --- | ----- | ----- |
| 1   | 02/24 | 02/26 |
| 2   | 03/31 | 04/02 |
| 3   | 05/05 | ?     |

HW is a tool for learning something, and testing you

Most of the exam is on HW 1 - checking the bare minimum
- Writing rigorous proofs
- No extension on the deadline
max(HW1, Ex1) + max(HW2, Ex2) + max(HW3, Ex3)
Out of 1000, above 900 to get an A

- Scaling policy
- Bonus points from exam
- 2 parts of the exam
- Hard questions on the HW
- Lecture - tell you what questions will be on the exam
- All HW should be done in $\LaTeX$

- OH on Monday - 2-3 in CoRE

- First part - simple mathematical things
- Second part - formal but outdated
- Third part - more modern

Natural Numbers - countably infinite
- Through Peano's axioms
	- There exists a 1
	- There is a thing called adding 1 to a number
- Natural numbers - extend to negatives - extend to fractions - extend to irrationals
- Start with something very simple, then add to it

$f: \mathbb{N} \to \mathbb{R}$
$f$ is a bijection
We want to show that $f$ is not surjective, so there exists an $x \in \mathbb{R}$ such that there does not exist an $a \in \mathbb{N}$ where $f(a) = x$.

For each $i \in \mathbb{N}, x_i = 9 - a_{ii}, x = \sum_{i = 1}^{\infty}10^{-i}x_i$

Claim: $\forall y \in \mathbb{N}, x \neq f(y)$, so $f$ is not surjective.

$x_y \neq f(y)$

$$
\begin{align*}
f(1) = \mathbf{a_{11}}a_{12}a_{13}\ldots\\
f(2) = a_{21}\mathbf{a_{22}}a_{23}\ldots\\
\ldots\\
f(n) = a_{n1}a_{n2}a_{n3}\ldots\\
\ldots
\end{align*}
$$

$$
\begin{align}.a_{11}a_{22}a_{33}\ldots\\
\pm1\pm1\pm1 \ldots\end{align}
$$

this specific number does not have a preimage

- Set up notations early on
- Be as generous with English words

- Cantor's diagonalization
	- Non-explicitly show that something exists
- $x$ exists because we wrongly assumed $f$ exists

Suppose for the sake of contradiction
Then we would like to show that... so that $f(a)$ is not surjective. Let $f(1) = \ldots, f(2) = \ldots$
Then $x_i = a - a_{ii}$
Then for all $y \in \mathbb{N}, x_y \neq f(y)_{yy}$

- Following Sipser's book from lectures 3-15

What is computation
- The study of space and time (also like physics)
- All of philosophy is just a misunderstanding of language
- Space - on hard drive
- Time - how long it takes before it spits out an answer

- Things that you want to compute, but can't compute

- Can't prove your solutions
	- Finding the weather
	- Diophantine equations

- Modeling
	- Input: weighted graph
	- Languages - strings
	- If you see 01, that is a delimiter
	- Give all pairs as integers
	- Sequence of bits

$$L_{MST} \subseteq \{0,1\}^\ast = \bigcup_{i \in \mathbb{N}}\{0,1\}^i$$
- All possible bitstrings of length $i$
- $x \in L_{MST} \iff$ if it is interpretable as $(G_x,\alpha)$ (In the graph $G_x$, is there a graph with weight at most $\alpha$) and the answer is **Yes**
- Who is making the interpretation
- DFA
- Can a DFA compute it
- Context-free grammar - PDA
- Turing Machine - considered to be universal - answer is yes

- If you want the solution, we talk about a relation

$$
R_{MST} \subseteq \{0, 1\}^\ast \text{(input)} \times \{0, 1\}^\ast \text{(output)}
$$

$$
\begin{align}(x, y) \in R_{MST} \iff &x \to (G_x, \alpha) \\ &y\to \text{Tree $T$ in $G_x$ whose weight is } \leq \alpha\end{align}
$$

- Strong if you talk about languages
- Canonical way of encoding