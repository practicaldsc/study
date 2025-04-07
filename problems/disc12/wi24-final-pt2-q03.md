# BEGIN PROB

With the help of the Alien from Bayesian Galaxy, Issac
built a Little Hadron Collider in his garage to continue testing some
fundamental principles of nature. The alien set up a fixed target at one
end of the collider, and ask Issac to shoot quarks from the other end.
Everytime the quark hit the target, the Alien will tell Issac whether a
new hadron is formed or not. Due to the energy limitation in Issac's
garage, he could only generate up, down, top, and bottom quarks (Strange
and Charm quark would have consumed too much energy). For each quark
Issac created, he has a record of:

-   the type `up`, `down`, `top`, `bottom`

-   the state `particle`, `antiparticle`

-   the color charge `red`, `green`, `blue`, and

-   the outcome `hadron formed`, `hadron not formed`

Issac created $10$ quarks, and these $10$ quarks are recorded in the table
below.

::: center
  **type**   **state**      **color**   **Formed Hadron**
  ---------- -------------- ----------- -------------------
  down       particle       green       formed
  top        particle       red         formed
  top        antiparticle   blue        formed
  up         particle       red         formed
  up         antiparticle   blue        formed
  bottom     antiparticle   red         not formed
  down       antiparticle   blue        not formed
  down       particle       blue        not formed
  top        particle       green       not formed
  up         antiparticle   green       not formed
:::

Since the alien is from Bayesian galaxy, they want Issac to develop a
Naive Bayes classifier to predict whether he'll be successful in forming
a hadron under the following quark conditions:

-   the type is `up`
-   the state is `particle`
-   the color is `blue`

# BEGIN SUBPROB

Naive Bayes predicts that, given a `up-particle-blue` quark,
the probability a hadron formed is $k$ times the probability a hadron is
not formed, for an integer value of $k$. What is $k$?

( ) $1$
( ) $2$
( ) $3$
( ) $4$

# BEGIN SOLUTION

$k = 3$

Following the equation for Naive Bayes we will create the folllowing two formulas:
\begin{align*}
&P(\text{formed hadron}|\text{up, particle, blue})\\
&=P(\text{formed hadron}) * P(\text{up}|\text{formed hadron}) * P(\text{particle}|\text{formed hadron}) * P(\text{blue}|\text{formed hadron})
\end{align*}
and
\begin{align*}
&P(\text{not formed hadron}|\text{up, particle, blue})\\
&=P(\text{not formed hadron}) * P(\text{up}|\text{not formed hadron}) * P(\text{particle}|\text{not formed hadron}) * P(\text{blue}|\text{not formed hadron})
\end{align*}

Now all we have to do is calculate the prior probabilities!

We can calculate $P(\text{formed hadron})$ by looking at the number of times a `formed hadron` happens out of the total number of outcomes. We can see this probability is $P(\text{formed hadron}) = \frac{5}{10} = \frac{1}{2}$.

Similarily we can calculate for a `not formed hadron` $P(\text{not formed hadron}) = \frac{5}{10} = \frac{1}{2}$.

We can calculate $P(\text{up}|\text{formed hadron})$ by looking at the number of times `up` appears out of all `formed hadron`s. This will give us something like: $P(\text{up}|\text{formed hadron}) = \frac{2}{5}$.

We can use this same method to calculate $P(\text{up}|\text{not formed hadron})$ by looking at the number of times `up` appears out of all `not formed hadron`s. $P(\text{up}|\text{not formed hadron}) = \frac{1}{5}$

If you continue finding the conditional probabilities you will find:

- $P(\text{particle}|\text{formed hadron}) = \frac{3}{5}$
- $P(\text{particle}|\text{not formed hadron}) = \frac{2}{5}$
- $P(\text{blue}|\text{formed hadron}) = \frac{2}{5}$
- $P(\text{blue}|\text{not formed hadron}) = \frac{2}{5}$

Now we simply plug and chug using the equations we had before!
\begin{align*}
&P(\text{formed hadron}|\text{up, particle, blue})\\
&= P(\text{formed hadron}) * P(\text{up}|\text{formed hadron}) * P(\text{particle}|\text{formed hadron}) * P(\text{blue}|\text{formed hadron})\\
&= \frac{1}{2} * \frac{2}{5} * \frac{3}{5} * \frac{2}{5}\\
&= \frac{6}{125}
\end{align*}
and 
\begin{align*}
&P(\text{not formed hadron}|\text{up, particle, blue})\\
&= P(\text{not formed hadron}) * P(\text{up}|\text{not formed hadron}) * P(\text{particle}|\text{not formed hadron}) * P(\text{blue}|\text{not formed hadron})\\
&= \frac{1}{2} * \frac{1}{5} * \frac{2}{5} * \frac{2}{5}\\
&= \frac{2}{125}
\end{align*}

Now the only thing left to do is calculate $k$. We can do this by solving the equation $k * \frac{2}{125} = \frac{6}{125}$. You should find $k=3$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What would be the value of $k$ if you change `up` quark in the
previous collision to `top` quark, but keep everything else the same (i.e.
`top-particle-blue` quark)?

( ) $1$
( ) $2$
( ) $3$
( ) $4$

# BEGIN SOLUTION

$k = 3$

All we have to do for this problem, after completing the first part, is to see how $P(\text{top}|\text{formed hadron})$ and $P(\text{top}|\text{not formed hadron})$ changes our previous equations.

We calculate these two probabilites by looking at the number of formed/not formed hadrons respectively and counting how many of those are in the `top` position. You will find $P(\text{top}|\text{formed hadron}) = \frac{2}{5}$ and $P(\text{top}|\text{not formed hadron}) = \frac{1}{5}$. These are the same as our conditional probabilities when in the `up` position! Which means $k=3$ again.

If you want to go through the entire calculation again it can be found below:
\begin{align*}
&P(\text{formed hadron}|\text{top, particle, blue})\\
&= P(\text{formed hadron}) * P(\text{top}|\text{formed hadron}) * P(\text{particle}|\text{formed hadron}) * P(\text{blue}|\text{formed hadron})\\
&= \frac{1}{2} * \frac{2}{5} * \frac{3}{5} * \frac{2}{5}\\
&= \frac{6}{125}
\end{align*}
and 
\begin{align*}
&P(\text{not formed hadron}|\text{top, particle, blue})\\
&= P(\text{not formed hadron}) * P(\text{top}|\text{not formed hadron}) * P(\text{particle}|\text{not formed hadron}) * P(\text{blue}|\text{not formed hadron})\\
&= \frac{1}{2} * \frac{1}{5} * \frac{2}{5} * \frac{2}{5}\\
&= \frac{2}{125}
\end{align*}

We can do this by solving the equation $k * \frac{2}{125} = \frac{6}{125}$. You should find $k=3$.

# END SOLUTION

# END SUBPROB

# END PROB