# BEGIN PROB

# BEGIN SUBPROB

Consider the following five sentences.

-     "of the college board the"

-     "the board the board the"

-     "board the college board of"

-     "the college board of college"

-     "board the college board is"

Suppose we create a TF-IDF matrix, in which there is one row for each sentence and one column for each unique word. The value in row $i$ and column $j$ is the TF-IDF of word $j$ in sentence $i$. Note that since there are 5 sentences and 5 unique words across all sentences, the TF-IDF matrix has 25 total values.

Is there a column in the TF-IDF matrix in which all values are 0?

( ) Yes
( ) No

# BEGIN SOLN

**Answer: ** Yes

Recall,

$$\text{tf-idf}(t, d) = \text{term frequency}(t, d) \cdot \text{inverse document frequency}(t)$$

In the context of TF-IDF, if a word appears in every sentence, its inverse document frequency (IDF) would be $\log(\frac{5}{5}) = 0$. Since a word's TF-IDF in a document is its TF (term frequency) in that document multiplied by its IDF, if the word's IDF is 0, it's TF-IDF is also 0. Since "the" appears in all five sentences, its IDF is zero, leading to a column of zeros in the TF-IDF matrix for "the".

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

In which of the following sentences is "college" the word with the highest TF-IDF?

( ) Sentence 1
( ) Sentence 2
( ) Sentence 3
( ) Sentence 4
( ) Sentence 5

# BEGIN SOLN

**Answer: ** Sentence 4

Remember, the IDF of a word is the same for all documents, since $\text{idf}(t) = \log \left( \frac{\text{number of documents}}{number of documents containing $t$} \right)$. This means that the sentence where "college" is the word with the highest TF-IDF is the same as the sentence where "college" is the word with the highest TF, or term frequency. Sentence 4 is the only sentence where "college" appears twice; in all other sentences, "college" appears at most once. (Since all of these sentences have the same length, we know that if "college" appears more times in Sentence 4 than it does in other sentences, then "college"'s term frequency in Sentence 4, $\frac{2}{5}$, is also larger than in any other sentence.) As such, the answer is Sentence 4.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

As an alternative to TF-IDF, Suraj proposes the DF-ITF, or "document frequency-inverse term frequency". The DF-ITF of term $t$ in document $d$ is defined below:

$$\text{df-itf}(t, d) = \frac{\text{\# of documents in which $t$ appears}}{\text{total \# of documents}} \cdot \log \left( \frac{\text{total \# of words in $d$}}{\text{\# of occurrences of $t$ in $d$}} \right)$$

Fill in the blank: The term $t$ in document $d$ that best summarizes document $d$ is the term with \_\_\_\_.

( ) the largest DF-ITF in document $d$
( ) the smallest DF-ITF in document $d$

# BEGIN SOLN

**Answer: ** the smallest DF-IDF in document $d$

The key idea behind TF-IDF, as we learned in class, is that $t$ is a good summary of $d$ if $t$ occurs commonly in $d$ but rarely across all documents.

When $t$ occurs often in $d$, then $\frac{\text{\# of occurrences of $t$ in $d$}}{\text{total \# of words in $d$}}$ is large, which means $\frac{\text{total \# of words in $d$}}{\text{\# of occurrences of $t$ in $d$}}$ and hence $\log \left( \frac{\text{total \# of words in $d$}}{\text{\# of occurrences of $t$ in $d$}} \right)$ is small.

Similarly, if $t$ is rare across all documents, then $\frac{\text{\# of documents in which $t$ appears}}{\text{total \# of documents}}$ is small.

Putting the above two pieces together, we have that $\text{df-itf}(t, d)$ is small when $t$ occurs commonly in $d$ but rarely overall, which means that the term $t$ that best summarizes $d$ is the term with the smallest DF-IDF in $d$.

# END SOLN

# END SUBPROB

# END PROB
