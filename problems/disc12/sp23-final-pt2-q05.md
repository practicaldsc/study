# BEGIN PROB

You're interested in seeing the Milky Way in the night sky, which you have sometimes been able to do when conditions are right. For each night that you've attempted to see the Milky Way, you have a record of:

-   the setting (urban, suburban, or rural),
-   the season (winter, spring, summer, or fall),
-   the time (late night, or early morning), and
-   the outcome (successful, or unsuccessful).

These $12$ attempts are recorded in the table below.


  |**setting** &emsp;|  **season** &emsp;|  **time** &emsp;&emsp;&emsp;&emsp;&emsp;    |  **outcome** &emsp; |
  |-------------|------------|---------------|--------------|
  |suburban     |winter      |late night     |successful|
  |rural        |spring      |late night     |successful|
  |urban        |winter      |early morning  |successful|
  |rural        |winter      |early morning  |successful|
  |rural        |summer      |late night     |unsuccessful|
  |urban        |winter      |late night     |unsuccessful|
  |rural        |winter      |early morning  |unsuccessful|
  |rural        |spring      |late night     |unsuccessful|
  |urban        |fall        |early morning  |unsuccessful|
  |suburban     |summer      |late night     |unsuccessful|
  |urban        |winter      |late night     |unsuccessful|
  |rural        |winter      |late night     |unsuccessful|


You want to use a Naive Bayes classifier to predict whether you'll be
successful in seeing the Milky Way under the following conditions:

-   the setting is urban,
-   the season is winter, and
-   the time is late night.

Naive Bayes predicts that, under these conditions, the probability you are unsuccessful is $k$ times the probability you are successful, for an integer value of $k$. What is $k$?

( ) $k=1$
( ) $k=2$
( ) $k=3$
( ) $k=4$

# BEGIN SOLUTION

$k=3$

According to the Naive Bayes formula we will be solving these equations:
\begin{align*}
&P(\text{successful}|\text{urban, winter, late night})\\ &= P(\text{successful}) * P(\text{urban}|\text{successful}) * P(\text{winter}|\text{successful}) * P(\text{late night}|\text{successful})
\end{align*}
and 
\begin{align*}
&P(\text{unsuccessful}|\text{urban, winter, late night}) \\
&= P(\text{unsuccessful}) * P(\text{urban}|\text{unsuccessful}) * P(\text{winter}|\text{unsuccessful}) * P(\text{late night}|\text{unsuccessful})
\end{align*}

This means we need to calculate our prior probabilities $P(\text{successful})$, $P(\text{unsucessful})$, $P(\text{urban}|\text{successful})$, $P(\text{urban}|\text{usuccessful})$, $P(\text{winter}|\text{successful})$, $P(\text{winter}|\text{unsuccessful})$, $P(\text{late night}|\text{successful})$, and $P(\text{late night}|\text{unsuccessful})$.

We can calculate $P(\text{successful})$ by looking at the number of successful outcomes from all possible outcomes. We find $P(\text{successful}) = \frac{4}{12} = \frac{1}{3}$.

Similarily we can calculate $P(\text{unsucessful})$. $P(\text{unsucessful}) = \frac{8}{12} = \frac{2}{3}$.

We can now calculate $P(\text{urban}|\text{successful})$ by looking at how many settings are urban when the outcome is successful. $P(\text{urban}|\text{successful}) = \frac{1}{4}$.

Similarily we can calculate $P(\text{urban}|\text{unsuccessful})$. $P(\text{urban}|\text{unsuccessful}) = \frac{3}{8}$.

Following this same pattern we will find:

$P(\text{winter}|\text{successful}) = \frac{3}{4}$

$P(\text{winter}|\text{unsuccessful}) = \frac{4}{8} = \frac{1}{2}$

$P(\text{late night}|\text{successful}) = \frac{2}{4} = \frac{1}{2}$

$P(\text{late night}|\text{unsuccessful}) = \frac{6}{8} = \frac{3}{4}$

From here all we need to do is plug our prior probnabilities into the equations we made earlier and solve!

\begin{align*}
& P(\text{successful}|\text{urban, winter, late night})\\&= P(\text{successful}) * P(\text{urban}|\text{successful}) * P(\text{winter}|\text{successful}) * P(\text{late night}|\text{successful})\\
&= \frac{1}{3} * \frac{1}{4} * \frac{3}{4} * \frac{1}{2}\\
&= \frac{1}{32}
\end{align*}

and

\begin{align*}
& P(\text{unsuccessful}|\text{urban, winter, late night}) \\ &= P(\text{unsuccessful}) * P(\text{urban}|\text{unsuccessful}) * P(\text{winter}|\text{unsuccessful}) * P(\text{late night}|\text{unsuccessful})\\
&= \frac{2}{3} * \frac{3}{8} * \frac{1}{2} * \frac{3}{4}\\
&= \frac{3}{32}
\end{align*}

We are told in the problem that "the probability you are unsuccessful is $k$ times the probability you are successful."

This means $k * \frac{1}{32} = \frac{3}{32}$, which we can easily see shows $k = 3$.

# END SOLUTION

# END PROB