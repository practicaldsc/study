
# BEGIN PROB

<i>Source: [Winter 2024 Midterm 2](../wi24-midterm2/index.html), Problem 4</i>

The standard acceleration of gravity $g$ is a universal constant of nature. That means $g=9.80665$ across the entire universe. It is also known that:

$$G = m \cdot  g$$

Where $G$ is the weight of an object and $m$ is the mass of an object. Issac is interested in measuring $g$. He prepared a dumbbell with mass $10$ in his garage and measured the weight of it three times. The three measured weights were: $102$, $98$, and $100$.

# BEGIN SUBPROB

Calculate the mean value of $g$ Issac measured.

# BEGIN SOLUTION

We can rearrange the equation and get: $$g = \frac{G}{m}$$

Isaac calculated these values of $g$ from his three trials.

- $g = \frac{102}{10} = 10.2 \\ \\$

- $g = \frac{98}{10} = 9.8 \\ \\$

- $g = \frac{100}{10} = 10$

So the mean value of $g$ Isaac measured is:
$\frac{(10.2 + 9.8 + 10)}{3} = 10.$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB
After his measurement, an alien from the Frequentist Galaxy visited Issac's garage. The alien could only understand frequentist statistics. Explain to the alien why Issac's measurement deviates from $g=9.80665$ (Hint: verbal explanation is enough, no equation is needed).

# BEGIN SOLUTION

Frequentists do not assign probability to hypotheses, so $g$ is always equal to $9.80665$ and it does not change. Issac's measurement deviates from the actual $g$ value because of uncertainties in the measurement.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

After the first alien left, another alien from the Bayesian galaxy arrived. This alien told Issac: "I think $g$ could take any value: it could be $1$, could be $10$, could be $100$". Using the Bayes equation and Issac's measurement, convince the alien that $g$ should be close to $10$.

# BEGIN SOLUTION
The Bayes equation reads:

$$\text{Posterior} = \frac{\text{Prior}\cdot  \text{Likelihood}}{\text{Evidence}}$$

The alien provides a uniform prior, or $P(\text{Hypothesis})$. They assume $g$ could take many different possible values. However, the likelihood term is $P(\text{Data|Hypothesis})$. For the hypothesis of $g = 1$, since it does not agree with data, the likelihood is very low and does not contribute to posterior; the same argument holds for $g = 100$. Only when $g$ = $10$ will the likelihood be high.
# END SOLUTION

# END SUBPROB

<!-- BONUS PROBLEM BELOW -->

<!-- # BEGIN SUBPROB
Which explanation do you prefer? (Note: both answers are correct, enjoy your one free point).

( ) Frequentist
( ) Bayesian

# BEGIN SOLUTION
    Both are correct.
# END SOLUTION

# END SUBPROB -->

# END PROB

