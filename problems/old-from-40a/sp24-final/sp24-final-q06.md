# BEGIN PROB

<i>Source: [Spring 2024 Final](../sp24-final/index.html), Problem 6</i>

Atlanta, Detroit, and Minneapolis are the three largest hub airports for
Delta Airlines. You survey a sample of $n$ students at UCSD, and find
that:

-   20 students have been to Atlanta.

-   16 students have been to Detroit.

-   10 students have been to Minneapolis.

-   1 student hasn't been to any of these three cities.

-   Of the 10 students who have been to Minneapolis, none have been to
    Detroit and 5 have been to Atlanta.

Suppose you select one student at random from your sample of $n$.

# BEGIN SUBPROB

Suppose the event that the selected student has been to Atlanta and the
event that the selected student has been to Detroit are independent.

What is the value of $n$? Your answer should be an **integer**.

# BEGIN SOLUTION

$32$.

There are a few ways to approach the problem, all of which involve a similar sequence of calculations – specifically, the principle of inclusion-exclusion for 3 sets.

The key is remembering that there are two unknowns: the number of people overall, $n$, and the number of people who have been to both Atlanta and Detroit, which we'll call $k$.

Many students drew Venn Diagrams, but ultimately they don't help answer the question directly; one needs to use the independence between Atlanta and Detroit.

One way to proceed is:

$$1 = \frac{20}{n} + \frac{16}{n} + \frac{10}{n} + \frac{1}{n} - \frac{5}{n} - \frac{k}{n}$$,

where $\frac{k}{n} = \frac{20}{n} \cdot \frac{16}{n}$. **This is the key step!**

Simplifying gives $1 = \frac{42}{n} - \frac{320}{n^2}$, which is equivalent to $n^2 - 42n + 320 = 0$.

This factors into $(n - 32)(n - 10) = 0$, so $n = 32$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Now, suppose the event that the selected student has been to Atlanta and
the event that the selected student has been to Detroit are not
independent, meaning that $n$ is no longer necessarily your answer from
part (a).

The event that the selected student has been to Atlanta and the event
that the selected student has been to Minneapolis are conditionally
independent given that the selected student **has not** been to Detroit.

Now, what is the value of $n$?

( ) $12$ 
( ) $28$ 
( ) $30$ 
( ) $32$ 
( ) $42$ 
( ) $45$ 
( ) $56$

# BEGIN SOLUTION

$28$.

Without any assumptions on the value of $k$, the number of people who have been to Atlanta and Detroit, it can be shown that:

$$n = 42 - k$$

Using the conditional independence assumption given in this part, we have that $\frac{20-k}{n - 16} \cdot \frac{10}{n - 16} = \frac{5}{n - 16}$, which simplifies to $2(20 - k) = n - 16 \implies n = 56 - 2k$.

We now have a system of equations:
$$\begin{cases}
n = 42 - k \\
n = 56 - 2k
\end{cases}$$

Solving this system of equations for $n$ gives $n = 28$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Consider the events $A$, $D$, and $M$, defined as follows:

-   $A$: The event that the selected student has been to Atlanta.

-   $D$: The event that the selected student has been to Detroit.

-   $M$: The event that the selected student has been to Minneapolis.

Let $A^c$, $D^c$, and $M^c$ represent the complements of events $A$,
$D$, and $M$, respectively. (In class, we used $\bar{A}$ to represent
the complement, but that's hard to read on the exam.)

Which of the following combinations of sets form a partition of the
sample space?

( ) $A$ &emsp; $D$ &emsp; $M$
( ) $A \cap D^c \cap M^c$ &emsp; $D$ &emsp; $M$
( ) $A \cap D$ &emsp; $D^c$ &emsp; $A^c \cap D \cap M^c$
( ) $A^c$ &emsp; $A \cap D$ &emsp; $A \cap M$
( ) None of the above.

# BEGIN SOLUTION

Option 3 is correct ($A \cap D$ &emsp; $D^c$ &emsp; $A^c \cap D \cap M^c$).

# END SOLUTION

# END SUBPROB

# END PROB