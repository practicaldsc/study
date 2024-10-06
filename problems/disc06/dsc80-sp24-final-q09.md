# BEGIN PROB

You create a table called `gums` that only contains the chewing gum
purchases of `df`, then you create a bag-of-words matrix called `bow`
from the `name` column of `gums`. The `bow` matrix is stored as a
DataFrame shown below:

<center><img src="../../assets/images/disc06/bow.png" width=400></center>

You also have the following outputs:

```
>>> bow_df.sum(axis=0)     >>> bow_df.sum(axis=1)     >>> bow_df.loc[0, 'pur']
pur            5           0     21                   0
gum           41           1     22
sugar          2           2     22                   >>> (bow_df['paperboard'] > 0).sum()
              ..                 ..                   20
90             4           37    22
paperboard    22           38    10                   >>> bow_df['gum'].sum()
80            20           39    17                   41
Length: 139                Length: 40
```

For each question below, write your answer as an unsimplified math expression
(no need to simplify fractions or logarithms) in the space provided, or write
"Need more information" if there is not enough information provided to answer
the question.

# BEGIN SUBPROB

What is the TF-IDF for the word "pur" in document 0?

# BEGIN SOLN

**Answer:** 0

First, it's worth discussing what information we have.

1. `bow_df.sum(axis=0)` computes the sum of each **column** of `bow_df`. Each column of `bow_df` refers to a specific word, so the sum of a column in `bow_df` tells us the number of occurrences of a particular word **across the entire corpus (all documents)**.
1. `bow_df.sum(axis=1)` computes the sum of each **row** of `bow_df`. Each row of `bow_df` refers to a specific document, so the sum of a row in `bow_df` tells us the **number of words in a particular document**.
1. `bow_df.loc[0, 'pur']` being `0` tells us that the word `"pur"` appears 0 times in document 0.
1. `(bow_df["paperboard"] > 0).sum()` being `20` means that there are 20 documents that contain the word `"paperboard"`.
1. `bow_df["gum"].sum()` being `41` means that `"gum"` appears 41 times across all documents.


Now, back to the subpart at hand. The TF-IDF of "pur" in document 0 is **0**, because bullet point 3 above tells us that "pur" doesn't occur at all in document 0. This means that the term frequency of "pur" in document 0 is 0, which means the TF-IDF (which is the product of the term frequency and inverse document frequency) of "pur" in document 0 is also 0, because 0 multiplied by the IDF of "pur" must be 0.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

What is the TF-IDF for the word "gum" in document 0?

# BEGIN SOLN

**Answer:** Need more information

Let's try and compute the TF-IDF of "gum" in document 0. The formula is as follows:

$$
\text{tfidf}(\text{gum}, \text{document 0}) = \text{tf}(\text{gum}, \text{document 0}) \cdot \text{idf}(\text{gum})
$$

$$
= \frac{\# \text{ of words in document 0 equal to gum}}{\# \text{ of words in document 0}} \cdot \log \left( \frac{\text{ total \# of documents}}{\text{total \# of documents containing gum}} \right)
$$

$$
= \frac{1}{21} \cdot \log \left( \frac{40}{???} \right)
$$

<!-- $$\begin{align*}  \text{tfidf}(\text{"gum"}, \text{document 0}) &= \text{tf}(\text{"gum"}, \text{document 0}) \cdot \text{idf}(\text{"gum"}) \\ &= \frac{\text{\# of words in document 0 equal to "gum"}}{\text{\# of words in document 0}} \cdot \log \left( \frac{\text{total \# of documents}}{\text{total \# of documents containing "gum"}} \right) \\ &= \frac{1}{21} \cdot \log \left( \frac{40}{???} \right) \end{align*}$$ -->

We don't know the number of documents containing "gum" – all we know (from bullet point 5 in the previous solution) is that "gum" appears 41 times across all documents, but we don't know how many unique documents contain "gum". So, we need more information.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

What is the TF-IDF for the word "paperboard" in document 1?

# BEGIN SOLN

**Answer:** $\frac{1}{22}$

Let's try and compute the TF-IDF of "paperboard" in document 1. The formula is as follows (assuming a base-2 logarithm):

$$
\text{tfidf}(\text{"paperboard"}, \text{document 1}) = \text{tf}(\text{"paperboard"}, \text{document 1}) \cdot \text{idf}(\text{"paperboard"})
$$

$$
= \frac{\text{\# of words in document 1 equal to "paperboard"}}{\text{\# of words in document 1}} \cdot \log \left( \frac{\text{total \# of documents}}{\text{total \# of documents containing "paperboard"}} \right)
$$

$$
= \frac{\text{1}}{\text{22}} \cdot \log \left( \frac{\text{40}}{\text{20}} \right) = \frac{\text{1}}{\text{22}} \cdot \log(\text{2}) = \frac{\text{1}}{\text{22}} \cdot \text{1} = \frac{\text{1}}{\text{22}}
$$


<!-- $$\begin{align*} \text{tfidf}(\text{"paperboard"}, \text{document 1}) &= \text{tf}(\text{"paperboard"}, \text{document 1}) \cdot \text{idf}(\text{"paperboard"}) \\ &= \frac{\text{# of words in document 1 equal to "paperboard"}}{\text{# of words in document 1}} \cdot \log \left( \frac{\text{total # of documents}}{\text{total # of documents containing "paperboard"}} \right) \\ &= \frac{1}{22} \cdot \log \left( \frac{40}{20} \right) \\ &= \frac{1}{22} \cdot \log(2) = \frac{1}{22} \cdot 1 \\ &= \frac{1}{22} \end{align*}$$ -->

# END SOLN

# END SUBPROB

# END PROB