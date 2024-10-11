Skytrax is a website that allows anyone to submit a review for a flight they took. In this exam, we'll work with the DataFrame `reviews`, which contains flight reviews taken from Skytrax.

The first few rows of `reviews` are shown below, but `reviews` has many more rows than are shown.

<center><img src="../assets/images/fa24-midterm/df.png" width=800></center>

The columns in `reviews` are as follows:

- `"airline"` (str): The airline flown. Note that an airline can be reviewed multiple times.
- `"author"` (str): The author of the review. Note that an author can write multiple reviews (and can even write multiple reviews of the same airline!).
- `"date"` (str): The date on which the review was written. Most of the reviews were written in 2015.
- `"content"` (str): The content of the review.
- `"cabin"` (str): The cabin the author flew; either `"Economy"`, `"Premium Economy"`, `"Business"`, or `"First"`.
- `"overall"` (int): The overall rating the author gave their flight experience, between 0 and 10 (inclusive).

**Throughout the exam**, assume we have already run `import pandas as pd` and `import numpy as np`.
