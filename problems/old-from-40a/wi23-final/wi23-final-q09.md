# BEGIN PROB

<!-- **Naive Bayes Classifier** -->

<i>Source: [Winter 2023 Final](../wi23-final/index.html), Problem 9</i>

In the following \"Symptoms\" dataset, the 
task is to diagnose whether a person is sick. We use a representation
based on four features per subject to describe an individual person.
These features are \"running nose\", \"coughing\", and \"fever\", each
of which can take the value true ('+') or false ('--').

<center><img src="../assets/images/wi23-final/symptoms.png" width="500"></center>

# BEGIN SUBPROB

What is the predicted class for a person with running nose
but no coughing, and no fever: sick, or healthy? Use a Naive Bayes classifier.

# BEGIN SOLUTION

The predicted class is Healthy($-$).

If $p_+$ and $p_-$ are the numerators of the Naive Bayes comparison that represent a Sick($+$) prediction and a Healthy($-$) prediction, respectively, we have to compare: $$\begin{aligned}
    p_+=P(N,\bar C,\bar F|+)P(+)\quad \text{and}\quad p_-=P(N,\bar C,\bar F|-)P(-).
\end{aligned}$$ 

We can find:
$$\begin{aligned}
    &P(+)=\frac35\\
    &P(-)=\frac25 \\
    &P(N,\bar C,\bar F|+)=P(N|+)P(\bar C|+)P(\bar F|+)=\frac23\times \frac13\times\frac13=\frac{2}{27}\\
    &P(N,\bar C,\bar F|-)=P(N|-)P(\bar C|-)P(\bar F|-)=\frac12\times \frac12\times 1=\frac{1}{4}.
\end{aligned}$$ 

Then we can build up our comparison:
$$\begin{aligned}
    p_+&= P(+)P(N,\bar C,\bar F|+) = \frac35\times\frac{2}{27}=\frac{2}{45}\quad \\
    p_-&= P(-)P(N,\bar C,\bar F|-) = \frac25\times\frac{1}{4}=\frac{1}{10}\\
    p_-&>p_+
\end{aligned}$$ 

So, the predicted class is Healthy($-$).

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

What is the predicted class for a person with a running nose
and fever, but no coughing? Use a Naive Bayes classifier.

# BEGIN SOLUTION

The predicted class is Sick($+$).

From the dataset we see $P(F|-)=0$, so we know:
$$P(N,\bar C, F|-)=P(N|-)P(\bar C|-)P(F|-)=0$$

This will make $p_- = P(N,\bar C, F|-)P(-) = 0$

Contrast this against $P(F|+), P(N|+),$ and $P(\bar C|+)$, which are all nonzero values, making $P(N,\bar C, F|+)$, (and therefore $p_+$) nonzero. 

So $p_+>p_-$. This means our predicted class is Sick($+$).


# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

To deal with cases of unseen features, we used "smoothing\"
in class. If we use the "smoothing\" method discussed in class, then
what is the probability of a person having running nose and fever, but
no coughing if that person was diagnosed "healthy\"?

# BEGIN SOLUTION

With smoothing, the result is $\dfrac{1}{16}$.

To apply smoothing, we add $1$ to the numerator, and add the number of possible categories of the given event, healthiness (which would be $2$ possible options in this case: sick, or healthy) to the denominator of our *conditional* probabilities. That way, other probabilities avoid being multiplied by zero. Let's smooth our three conditional probabilities:

$$P(N|-)= \frac{1}{2} \to \frac{1 + 1}{2 + 2} = \frac{2}{4}$$
$$P(\bar C|-)= \frac{1}{2} \to \frac{1 + 1}{2 + 2} = \frac{2}{4}$$

$P(F|-)=0$ is a zero probability that also needs to be smoothed. The smoothed version becomes:
$$P(F|-)= \frac{0}{2} \to \frac{0 + 1}{2 + 2} = \frac{1}{4}$$

We carry on evaluating $P(N,\bar C, F|-)$, just as the problem asks.

$$\begin{aligned}
          P(N,\bar C, F|-)=P(N|-)P(\bar C|-)P(F|-)=\frac24\times \frac24\times \frac14=\frac{1}{16}.
\end{aligned}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

In part (a), what are the **odds** of a person being "sick\"
who has running nose but no coughing, and no fever? *(Hint: the formula for the odds of an event $A$ is $\text{odds}(A) = \frac{P(A)}{1 - P(A)}$)*

# BEGIN SOLUTION

$$\text{Odds of being sick}=\frac27$$

Using previous information, we have that the probability of a person being sick with a running nose but no coughing and no fever is:

$$\begin{aligned}
P(+|N,\bar C,\bar F)=\frac{p_+}{P(N,\bar C,\bar F)}=\frac{\frac{2}{45}}{\frac{1}{5}}=\frac29. 
\end{aligned}$$ 

$$\begin{aligned}
\text{Odds of being sick}=\frac{P(+|N,\bar C,\bar F)}{1-P(+|N,\bar C,\bar F)}=\frac27.   
\end{aligned}$$

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

Say someone fit a logistic regression model to a dataset
containing $n$ points $(x_1,y_1),(x_2,y_2),\cdots,(x_n,y_n)$ where
$x_i$s are features and $y_i\in\{-1,+1\}$ are labels. The estimated
parameters are $w_0,~w_1$, that is, given feature $x$, the predicted
probability of belonging to class $y=+1$ is 

$$\begin{aligned}
        P(y=+1|x)=\frac{1}{1+\exp(-w_0-w_1x)}.
\end{aligned}$$ 

Interpret the meaning of $w_1=1$.

# BEGIN SOLUTION

One interpretation is as follows: 

"If $x$ is increased by $1$, then the odds of $y=+1$ increases by a factor of
$\exp(1)=2.718$."

# END SOLUTION

# END SUBPROB

# END PROB