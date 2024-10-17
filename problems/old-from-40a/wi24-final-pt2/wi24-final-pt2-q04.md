# BEGIN PROB

<i>Source: [Winter 2024 Final Part 2](../wi24-final-pt2/index.html), Problem 4</i>

In hospital, there are $10$ patients who have recently been exposed to COVID. The hospital purchased a new COVID testing machine. The machine could comprehensively analyze multiple body measurements to produce a COVID score for each patient, ranging from $1$ to $10$. According to the instruction manual of the machine, a higher COVID score means the patient is more likely to be infected by COVID, while a lower COVID score means the patient is less likely to be infected. The COVID score of each patient is listed below:

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |


Suppose Patient 1, Patient 2, Patient 3, and Patient 4 are actually infected by COVID, while all other patients are not infected. 


# BEGIN SUBPROB

Based on the patient's COVID score, Dr. Issac uses a threshold of $2.5$ to diagnose COVID. That is, he diagnoses all patients with a COVID Score above $2.5$ to be COVID-infected, and all patients with a COVID Score below $2.5$ to be non-infected. What is the True Positive (TP), True Negative (TN), False Positive (FP), and False Negative (FN) of Dr. Issac’s diagnosis? Each block should be filled with an integer.

TP = ?

# BEGIN SOLUTION

TP = $4$

True positives are when the patient has COVID and was predicted to have COVID. It can be helpful to expand on the table from above to visualize how many patients have COVID.

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | True | True | True | True | False | True | False |


We can now easily see Dr. Issac's threshold would correctly diagnose $4$ patients with COVID.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

TN = ?

# BEGIN SOLUTION

TN = $2$

A true negative is when the patient does not have COVID and is predicted to not have COVID.

Using the same table as the part before:

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | True | True | True | True | False | True | False |


We can see Dr. Issac's threshold would correctly diagnose $2$ patients to not have COVID.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

FP = ?

# BEGIN SOLUTION

FP = $4$

A false positive is when the patient is said to have COVID, but does not have COVID.

Using the same table as the part before:

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | True | True | True | True | False | True | False |


We can see Dr. Issac's threshold would incorrectly diagnose $4$ patients with COVID.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

FN = ?

# BEGIN SOLUTION

FN = $0$

A false negative is when the patient is said to not have COVID, but has COVID.

Using the same table as the part before:

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | True | True | True | True | False | True | False |


We can see Dr. Issac's threshold would incorrectly diagnose $0$ patients.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Dr. Albert is somewhat skeptical about technology, leading him to adopt a cautious approach in diagnosing patients. Initially, he sets a diagnostic threshold at $5.5$. Patients scoring above this threshold are initially diagnosed as positive. However, Dr. Albert conducts a secondary diagnosis for all patients who received a positive diagnosis initially. During this secondary diagnosis, he reclassifies Patient 9's positive diagnoses as negative. What is the True Positive (TP), True Negative (TN), False Positive (FP), and False Negative (FN) of Dr. Albert’s diagnosis? Each block should be filled with an integer.

TP = ?

# BEGIN SOLUTION

TP = $3$

True positives are when the patient has COVID and was predicted to have COVID.

Once again it can be beneficial to look at the table visually with added rows for how Dr. Albert predicted each patient's COVID status.

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | False | False | False | True | False | False | False |

<i> Note that Patient 9 was classified as False after a secondary diagnosis! </i>

Here we can see that Dr. Albert's threshold and diagnosises would correctly identify $3$ of the $4$ patients have COVID, making TP = $3$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

TN = ?

# BEGIN SOLUTION

TN = $5$

A true negative is when the patient does not have COVID and is predicted to not have COVID.

Using the same table as the part before:

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | False | False | False | True | False | False | False |

<i> Note that Patient 9 was classified as False after a secondary diagnosis! </i>

Here we can see that Dr. Albert's threshold and diagnosises would correctly identify $5$ of the $6$ not having COVID, making TN = $5$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

FP = ?

# BEGIN SOLUTION

FP = $1$

A false positive is when the patient is said to have COVID, but does not have COVID.

Using the same table as the part before:

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | False | False | False | True | False | False | False |

<i> Note that Patient 9 was classified as False after a secondary diagnosis! </i>

We can see that Dr. Albert's threshold and diagnosises would incorrectly identify $1$ patient as having COVID when they do not.
Making FP = $1$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

FN = ?

# BEGIN SOLUTION

FN = $1$

A false negative is when the patient is said to not have COVID, but has COVID.

Using the same table as the part before:

| **Patient Number** |  1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------------------|--------|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **COVID Score**    | 7      | 9     | 9     | 3     | 5     | 4     | 6     | 1     | 8     | 2      |
| **Has COVID**| True | True | True | True | False | False | False | False | False | False |
| **Predicted COVID**| True | True | True | False | False | False | True | False | False | False |

<i> Note that Patient 9 was classified as False after a secondary diagnosis! </i>

We can see Dr. Albert's threshold would incorrectly diagnose $1$ patient, making FN = $1$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Which Doctor's diagnoses is better?

( ) Albert
( ) Issac
( ) They are equally good

# BEGIN SOLUTION

Albert

Recall the equation for accuracy is $\frac{\text{TP}+\text{TN}}{\text{TP} + \text{FP} + \text{FN} + \text{TN}}$.

We can figure out which Doctor's diagnosis was more accurate, thus better.

Dr. Isaac:
$$
\frac{4 + 2}{4 + 4 + 0 + 2} = \frac{6}{10}
$$

Dr. Albert:
$$
\frac{3 + 5}{3 + 1 + 1 + 5} = \frac{8}{10}
$$

We can see that Dr. Albert's accuracy is greater than Dr Isaac's accuracy, which means Dr. ALbert's diagnosis is better.

# END SOLUTION

# END SUBPROB

# END PROB