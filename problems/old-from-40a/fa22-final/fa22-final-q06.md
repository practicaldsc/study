# BEGIN PROB

<!-- Naive Bayes/Conditional Independence -->

Consider the following email data set:

-   I have my DSC 40A final exam today. Wish me luck! (ham)

-   Your credit card were declined today. Let me know your SSN to help.
    (spam)

-   I understand that I should bring my UCSD ID card to the exam. (ham)

-   You can understand machine learning without learning about
    probability. (spam)

-   You should bring your credit card to the exam.(spam)

Consider the following dictionary

{ final, card, exam, bring}.

The dataset then can be illustrated by considering the bag-of-words
model as in the following table

::: center
  Email ID   final   card    exam    bring   label
  ---------- ------- ------- ------- ------- ---------
  1          **1**   **0**   **1**   **0**   **ham**
  2          0       1       0       0       spam
  3          **0**   **1**   **1**   **1**   **ham**
  4          0       0       0       0       spam
  5          0       1       1       1       spam

\
:::

To answer the following questions, you **should** use smoothing for
calculating the probability of both classes even if you run to the zero
probability issue in only one of the classes. Otherwise, please do
**not** use smoothing at all.

# BEGIN SUBPROB

\[5 Points\] Is "Please understand that you can not bring cellphone to
exam.\" spam or ham? You should show your work.

# BEGIN SOLUTION

We represent the features with binary variables $x_1, x_2, x_3, x_4$.
Then, this sentence is represented by $(x_1, x_2, x_3, x_4)=(0,0,1,1)$
binary vector, which is denoted by $0011$ for the ease of notation. Let
$H$ and $S$ denote the event that an email is a ham or spam,
respectively. We calculate the conditional probability of both classes
as follows: $$\begin{aligned}
 P(H|0011)& \propto P(0011|H) P(H)\\
 &=P(x_1=0|H)P(x_2=0|H)P(x_3=1|H)P(x_4=1|H)P(H)\\
 &=\frac{1}{2}\times \frac{1}{2}\times\frac{1}{1}\times\frac{1}{2}\times\frac{2}{5}=\frac{1}{20}
\end{aligned}$$ Similarly, $$\begin{aligned}
 P(S|0011)& \propto P(0011|S) P(S)\\
 &=P(x_1=0|S)P(x_2=0|S)P(x_3=1|S)P(x_4=1|S)P(S)\\
 &=\frac{2}{3}\times \frac{1}{3}\times\frac{1}{3}\times\frac{1}{3}\times\frac{3}{5}=\frac{1}{45}. 
\end{aligned}$$ Since, $P(S|0011) < P(H|0011)$ we predict the email is a
ham. Note that we didnt need smoothing for this part.

# END SOLUTION 

# END SUBPROB 

# BEGIN SUBPROB

\[5 Points\] Is "I am working on probabilty problems in the final exam
\" spam or ham? You should show your work.

# BEGIN SOLUTION

Similarly, this sample is denoted by $1010$. Note that we should smooth
the conditional probablities as there is no spam email that has word
\"final\" in it but the sample email we want to predict has the word
\"final\" in it. Thjat means, we will run to the zero probability issue
if when computing $P(1010|S)$. We calculate the conditional probability
of both classes as follows:

$$\begin{aligned}
 P(S|1010)& \propto P(1010|S) P(S)\\
 &=P(x_1=1|S)P(x_2=0|S)P(x_3=1|S)P(x_4=0|S)P(S)\\
 &=\frac{1}{5}\times \frac{2}{5}\times\frac{2}{5}\times\frac{3}{5}\times\frac{3}{5}=\frac{36}{3125}. 
\end{aligned}$$ Similarly, $$\begin{aligned}
 P(H|1010)& \propto P(1010|H) P(H)\\
 &=P(x_1=1|H)P(x_2=0|H)P(x_3=1|H)P(x_4=0|H)P(H)\\
 &=\frac{2}{4}\times \frac{2}{4}\times\frac{3}{4}\times\frac{2}{4}\times\frac{2}{5}=\frac{3}{80}=\frac{36}{960}
\end{aligned}$$ Since, $P(S|1010) < P(H|1010)$ we predict the email is a
ham.

# END SOLUTION

# END SUBPROB

# END PROB