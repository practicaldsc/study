# BEGIN PROB

You are given a DataFrame called `books` that contains columns `'author'` (string), `'title'` (string), `'num_chapters'` (int), and `'publication_year'` (int).

Suppose that after doing `books.groupby('author').max()`, one row says

| author          | title        | num_chapters | publication_year |
| --------------- | ------------ | ------------ | ---------------- |
| Charles Dickens | Oliver Twist | 53           | 1838             |

# BEGIN SUBPROB

Based on this data, can you conclude that Charles Dickens is the alphabetically last of all author names in this dataset?

( ) Yes
( ) No

# BEGIN SOLUTION

**Answer: ** No

When we group by `'author'`, all books by the same author get aggregated together into a single row. The aggregation function is applied separately to each other column besides the column we're grouping by. Since we're grouping by `'author'` here, the `'author'` column never has the `max()` function applied to it. Instead, each unique value in the `'author'` column becomes a value in the index of the grouped DataFrame. We are told that the Charles Dickens row is just one row of the output, but we don't know anything about the other rows of the output, or the other authors. We can't say anything about where Charles Dickens falls when authors are ordered alphabetically (but it's probably not last!)

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Based on this data, can you conclude that Charles Dickens wrote _Oliver Twist_?

( ) Yes
( ) No

# BEGIN SOLUTION

**Answer: ** Yes

Grouping by `'author'` collapses all books written by the same author into a single row. Since we're applying the `max()` function to aggregate these books, we can conclude that _Oliver Twist_ is alphabetically last among all books in the `books` DataFrame written by Charles Dickens. So Charles Dickens did write _Oliver Twist_ based on this data.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Based on this data, can you conclude that _Oliver Twist_ has 53 chapters?

( ) Yes
( ) No

# BEGIN SOLUTION

**Answer: ** No

The key to this problem is that `groupby` applies the aggregation function, `max()` in this case, independently to each column. The output should be interpreted as follows:

- Among all books in `books` written by Charles Dickens, _Oliver Twist_ is the title that is alphabetically last.
- Among all books in `books` written by Charles Dickens, 53 is the greatest number of chapters.
- Among all books in `books` written by Charles Dickens, 1838 is the latest year of publication.

However, the book titled _Oliver Twist_, the book with 53 chapters, and the book published in 1838 are not necessarily all the same book. We cannot conclude, based on this data, that _Oliver Twist_ has 53 chapters.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Based on this data, can you conclude that Charles Dickens wrote a book with 53 chapters that was published in 1838?

( ) Yes
( ) No

# BEGIN SOLUTION

**Answer: ** No

As explained in the previous question, the `max()` function is applied separately to each column, so the book written by Charles Dickens with 53 chapters may not be the same book as the book written by Charles Dickens published in 1838.

# END SOLUTION

# END SUBPROB

# END PROB
