# BEGIN PROB

The DataFrame `new_releases` contains the following information for
songs that were recently released:

-   `"genre"`: the genre of the song (one of the following 5
    possibilities: `"Hip-Hop/Rap"`, `"Pop"`, `"Country"`,
    `"Alternative"`, or `"International"`)

-   `"rec_label"`: the record label of the artist who released the song
    (one of the following 4 possibilities: `"EMI"`, `"SME"`, `"UMG"`, or
    `"WMG"`)

-   `"danceability"`: how easy the song is to dance to, according to the
    Spotify API (between 0 and 1)

-   `"speechiness"`: what proportion of the song is made up of spoken
    words, according to the Spotify API (between 0 and 1)

-   `"first_month"`: the number of total streams the song had on Spotify
    in the first month it was released

The first few rows of `new_releases` are shown below (though
`new_releases` has many more rows than are shown below).

<center><img src='../assets/images/disc09/new_releases.png' width=55%></center>

We decide to build a linear regression model that predicts
`"first_month"` given all other information. To start, we conduct a
train-test split, splitting `new_releases` into `X_train`, `X_test`,
`y_train`, and `y_test`.

We then fit two linear models (with intercept terms) to the training
data:

-   Model 1 (`lr_one`): Uses `"danceability"` only.

-   Model 2 (`lr_two`): Uses `"danceability"` and `"speechiness"` only.

# BEGIN SUBPROB

Consider the following outputs.

```py
>>> X_train.shape[0]
50

>>> np.sum((y_train - lr_two.predict(X_train)) ** 2)
500000 # five hundred thousand
```

What is Model 2 (`lr_two`)'s training RMSE (square root of mean squared error)? Give your answer as an
integer.

# BEGIN SOLN

**Answer: ** 100

We are given that there are $n=50$ data points, and that the sum of
squared errors $\sum_{i = 1}^n (y_i - H(x_i))^2$ is $500{,}000$. Then:

$$\begin{aligned}
    \text{RMSE} &= \sqrt{\frac{1}{n} \sum_{i = 1}^n (y_i - H(x_i))^2} \\ 
    &= \sqrt{\frac{1}{50} \cdot 500{,}000} \\
    &= \sqrt{10{,}000}
    \\
    &= 100\end{aligned}$$

# END SOLN

# END SUBPROB

Now, suppose we fit two more linear models (with intercept terms) to the
training data:

-   Model 3 ($\texttt{lr\_drop}$): Uses `"danceability"` and
    `"speechiness"` as-is, and one-hot encodes `"genre"` and
    `"rec_label"`, using `OneHotEncoder(drop="first")`.

-   Model 4 ($\texttt{lr\_no\_drop}$): Uses `"danceability"` and
    `"speechiness"` as-is, and one-hot encodes `"genre"` and
    `"rec_label"`, using `OneHotEncoder()`.

Note that the only difference between Model 3 and Model 4 is the fact
that Model 3 uses `drop="first"`.

# BEGIN SUBPROB

How many **one-hot encoded** columns are used in each model? In other
words, how many **binary** columns are used in each model? Give both
answers as integers.

*Hint: Make sure to look closely at the description of `new_releases` at
the top of the previous page, and don't include the already-quantitative
features.*

number of one-hot encoded columns in Model 3 (`lr_drop`) =

number of one-hot encoded columns in Model 4 (`lr_no_drop`) =

# BEGIN SOLN

**Answer: ** 7 and 9

There are 5 unique values of `"genre"` and 4 unique values of
`"rec_label"`, so if we create a single one-hot encoded column for each
one, there would be $5 + 4 = 9$ one-hot encoded columns (which there are
in `lr_no_drop`).

If we drop one one-hot-encoded column per category, which is what
`drop="first"` does, then we only have $(5 - 1) + (4 - 1) = 7$ one-hot
encoded columns (which there are in `lr_drop`).

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Recall, in Model 4 (`lr_no_drop`) we one-hot encoded `"genre"` and
`"rec_label"`, and did not use `drop="first"` when instantiating our
`OneHotEncoder`.

Suppose we are given the following coefficients in Model 4:

-   The coefficient on `"genre_Pop"` is $2000$.

-   The coefficient on `"genre_Country"` is $1000$.

-   The coefficient on `"danceability"` is $10^6 = 1{,}000{,}000$.

Daisy and Billy are two artists signed to the same `"rec_label"` who
each just released a new song with the same `"speechiness"`. Daisy is a
`"Pop"` artist while Billy is a `"Country"` artist.

Model 4 predicted that Daisy's song and Billy's song will have the same
`"first_month"` streams. What is the **absolute difference** between
Daisy's song's `"danceability"` and Billy's song's `"danceability"`?
Give your answer as a simplified fraction.

# BEGIN SOLN

**Answer: ** $\frac{1}{1000}$

"My favorite problem on the exam!\" -Suraj

Model 4 is made up of 11 features, i.e. 11 columns.

-   4 of the columns correspond to the different values of
    `"rec_label"`. Since Daisy and Billy have the same `"rec_label"`,
    their values in these four columns are all the same.

-   One of the columns corresponds to `"speechiness"`. Since Daisy's
    song and Billy's song have the same `"speechiness"`, their values in
    this column are the same.

-   5 of the columns correspond to the different values of `"genre"`.
    Daisy is a `"Pop"` artist, so she has a 1 in the `"genre_Pop"`
    column and a 0 in the other four `"genre_"` columns, and similarly
    Billy has a 1 in the `"genre_Country"` column and 0s in the others.

-   One of the columns corresponds to `"danceability"`, and Daisy and
    Billy have different quantitative values in this column.

Let $d_1$ and $d_2$.

The key is in recognizing that all features in Daisy's prediction and
Billy's prediction are the same, other than the coefficients on
`"genre_Pop"`, `"genre_Country"`, and `"danceability"`. Let's let $d_1$
be Daisy's song's `"danceability"`, and let $d_2$ be Billy's song's
`"danceability"`. Then:

$$\begin{aligned}
    2000 + 10^{6} \cdot d_1 = 1000 + 10^{6} \cdot d_2 \\
    1000 &= 10^{6} (d_2 - d_1) \\
    \frac{1}{1000} &= d_2 - d_1\end{aligned}$$

Thus, the absolute difference between their songs' `"danceability"`s is
$\frac{1}{1000}$.

# END SOLN

# END SUBPROB

# END PROB