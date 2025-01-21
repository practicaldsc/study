# BEGIN PROB

For the problems that follow, we will work with a dataset consisting of various skyscrapers in the US, which we've loaded into a DataFrame called `sky`. The first few rows of `sky` are shown below (though the full DataFrame has more rows):

<center><img src='../assets/images/disc03/data-info-sky.png' width=60%></center>

<p>&nbsp;</p>

Each row of `sky` corresponds to a single skyscraper. For each skyscraper, we have:

* its name, which is stored in the index of `sky` (string)

* the `'material'` it is made up of (string)

* the `'city'` in the US where it is located (string)

* the number of `'floors'` (levels) it contains (int)

* its `'height'` in meters (float), and 

* the `'year'` in which it was opened (int)

Below, identify the data type of the result of each of the following expressions, or select "error" if you believe the expression results in an error.

# BEGIN SUBPROB

```py
sky.sort_values('height')
```

( ) int or float
( ) Boolean
( ) string
( ) array
( ) Series
( ) DataFrame
( ) error

# BEGIN SOLN

**Answer:** DataFrame

`sky` is a DataFrame. All the `sort_values` method does is change the order of the rows in the Series/DataFrame it is called on, it does not change the data structure. As such, `sky.sort_values('height')` is also a DataFrame.


# END SOLN

# END SUBPROB

# BEGIN SUBPROB

```py
sky.index[0]
```

( ) int or float
( ) Boolean
( ) string
( ) array
( ) Series
( ) DataFrame
( ) error

# BEGIN SOLN

**Answer:** string

`sky.index` contains the values `'Bayard-Condict Building'`, `'The Yacht Club at Portofino'`, `'City Investing Building'`, etc. `sky.index[0]` is then `'Bayard-Condict Building'`, which is a string.


# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Write a single line of code that evaluates to the name of the tallest skyscraper in the `sky` DataFrame.

# BEGIN SOLN

**Answer:** `sky.sort_values(by='height', ascending=False).index[0]`

In order to answer this question, we must first sort the values of the column we are interested in. As such, we sort the entire DataFrame by the `height` column, and because we are interested in the name of the tallest building, we should set the `ascending` parameter to `False` because we would like the heights to be ordered in descending order, thus leading to the line `sky.sort_values(by='height', ascending=False)`. After sorting in descending order, we know that the tallest building is going to be the first row of the new `sky` DataFrame, and thus we now only need to get the name of the skyscraper, which happens to be in the index. In order to access the index of the DataFrame we can use `sky.index`, and in our case because we know that we want the first index, we would need to write `sky.index[0]`. Finally, putting it all together, in order to get the name of the tallest skyscraper in the `sky` DataFrame, we would need to write `sky.sort_values(by='Height', ascending=False).index[0]`. 

# END SOLN

# END SUBPROB

# END PROB
