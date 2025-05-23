# BEGIN PROB

After fitting a `BillyClassifier` on our training set, we use it to make predictions on an unseen test set. Our results are summarized
in the following confusion matrix.

<center><img src='../assets/images/old-from-80/sp22-final/confusion-2.png' width=50%></center>

# BEGIN SUBPROB

What is the recall of our classifier? Give your answer as a
fraction (it does not need to be simplified).

# BEGIN SOLN

**Answer: ** $\frac{35}{57}$

There are 105 true positives and 66 false negatives. Hence, the recall
is $\frac{105}{105 + 66} = \frac{105}{171} = \frac{35}{57}$.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

The accuracy of our classifier is $\frac{69}{117}$. How many
**true negatives** did our classifier have? Give your answer as an
integer.

# BEGIN SOLN

**Answer: ** 33

Let $x$ be the number of true negatives. The number of correctly
classified data points is $105 + x$, and the total number of data points
is $105 + 30 + 66 + x = 201 + x$. Hence, this boils down to solving for
$x$ in $\frac{69}{117} = \frac{105 + x}{201 + x}$.

It may be tempting to cross-multiply here, but that's not necessary (in
fact, we picked the numbers specifically so you would not have to)!
Multiply $\frac{69}{117}$ by $\frac{2}{2}$ to yield $\frac{138}{234}$.
Then, conveniently, setting $x = 33$ in $\frac{105 + x}{201 + x}$ also
yields $\frac{138}{234}$, so $x = 33$ and hence the number of true
negatives our classifier has is 33.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

True or False: In order for a binary classifier's precision and recall
to be equal, the number of mistakes it makes must be an even number.

( ) True
( ) False

# BEGIN SOLN

**Answer: ** True

Remember that $\text{precision} = \frac{TP}{TP + FP}$ and
$\text{recall} = \frac{TP}{TP + FN}$. In order for precision to be the
same as recall, it must be the case that $FP = FN$, i.e. that our
classifier makes the same number of false positives and false negatives.
The only kinds of "errors\" or "mistakes\" a classifier can make are
false positives and false negatives; thus, we must have

$$\text{mistakes} = FP + FN = FP + FP = 2 \cdot FP$$

2 times any integer must be an even integer, so the number of mistakes
must be even.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Suppose we are building a classifier that listens to an audio source (say, from your phone's microphone) and predicts whether or not it is Soulja Boy's 2008 classic "Kiss Me thru the Phone". Our classifier is pretty good at detecting when the input stream is "Kiss Me thru the Phone", but it often incorrectly predicts that similar sounding songs
are also "Kiss Me thru the Phone".

Complete the sentence: Our classifier has...

( ) low precision and low recall.
( ) low precision and high recall.
( ) high precision and low recall.
( ) high precision and high recall.

# BEGIN SOLN

**Answer: ** Option B: low precision and high recall.

Our classifier is good at identifying when the input stream is "Kiss Me thru the Phone", i.e. it is good at identifying true positives amongst all positives. This means it has high recall.

Since our classifier makes many false positive predictions – in other words, it often incorrectly predicts "Kiss Me thru the Phone" when that's not what the input stream is – it has many false positives, so its precision is low.

Thus, our classifier has low precision and high recall.

# END SOLN

# END SUBPROB

# END PROB
